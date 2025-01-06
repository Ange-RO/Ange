Lors de la structuration d'une application back-end avec Node.js, il est important d'organiser votre projet de manière maintenable et évolutive. La structure d'un projet Node.js typique dépend de la taille et de la complexité de l'application, mais voici une structure standard pour commencer :

1. Structure de base du projet
frapper
Copier le code
/my-node-app
├── /config
├── /controllers
├── /models
├── /routes
├── /services
├── /middlewares
├── /utils
├── /validators
├── /tests
├── /node_modules
├── /public
├── .env
├── app.js (or server.js)
├── package.json
├── package-lock.json
├── README.md
└── .gitignore
2. Répartition des répertoires et des fichiers
/config:Fichiers de configuration, y compris les paramètres d'environnement et les variables de configuration (par exemple, connexion à la base de données, clés API).

Exemple: dbConfig.js,envConfig.js
/controllers:Fonctions du contrôleur qui gèrent la logique derrière le traitement des requêtes et le renvoi des réponses.

Exemple: userController.js,authController.js
/models: Définit les modèles de données de l'application, souvent à l'aide d'un ORM comme Sequelize, Mongoose ou des requêtes SQL brutes.

Exemple: userModel.js,postModel.js
/routes:Les définitions d'itinéraire qui mappent les requêtes HTTP à des fonctions de contrôleur spécifiques.

Exemple: userRoutes.js,authRoutes.js
/services:La logique métier et la manipulation des données, souvent utilisées pour garder les contrôleurs propres en séparant les préoccupations.

Exemple: authService.js,paymentService.js
/middlewares:Fonctions middleware personnalisées qui traitent les demandes avant qu'elles n'atteignent la logique du contrôleur (par exemple, authentification, journalisation).

Exemple: authMiddleware.js,loggerMiddleware.js
/utils:Fonctions utilitaires couramment utilisées dans l'application (par exemple, formatage des dates, hachage des mots de passe).

Exemple: hashingUtils.js,validationUtils.js
/validators: Validation d'entrée, généralement utilisée pour la validation du corps de la requête (par exemple, en utilisant express-validatorou joi).

Exemple: userValidator.js,postValidator.js
/tests:Tests unitaires et d'intégration pour l'application.

Exemple: userController.test.js,authService.test.js
/public:Fichiers statiques tels que des images, des styles ou du JavaScript frontal, si vous diffusez des ressources avec Node.js.

.env: Variables d'environnement pour les données sensibles (comme les informations d'identification de la base de données, les clés API). Utilisez ce fichier pour garder la configuration hors de votre base de code.

app.jsouserver.js : Point d'entrée principal où l'application est initialisée et le serveur démarre. Ce fichier regroupe toutes les routes, intergiciels et contrôleurs.

package.json:Contient les métadonnées du projet, les dépendances et les scripts.

README.md:Documentation sur le projet, instructions d'installation et comment contribuer.

.gitignore: Spécifie quels fichiers ou répertoires Git doit ignorer (par exemple, node_modules, .env).

3. Exemple d'implémentation du fichier
server.js(Point d'entrée)
javascript

Copier le code
const express = require('express');
const mongoose = require('mongoose');
const cors = require('cors');
const dotenv = require('dotenv');
const userRoutes = require('./routes/userRoutes');
const authMiddleware = require('./middlewares/authMiddleware');

dotenv.config();

const app = express();

// Middleware setup
app.use(cors());
app.use(express.json());
app.use(authMiddleware); // Global middleware

// Routes
app.use('/api/users', userRoutes);

// Connect to Database
mongoose.connect(process.env.MONGO_URI, { useNewUrlParser: true, useUnifiedTopology: true })
  .then(() => console.log("Connected to MongoDB"))
  .catch((err) => console.error("Error connecting to MongoDB:", err));

// Start server
const PORT = process.env.PORT || 5000;
app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
userRoutes.js(Itinéraires)
javascript

Copier le code
const express = require('express');
const router = express.Router();
const userController = require('../controllers/userController');
const userValidator = require('../validators/userValidator');

router.post('/signup', userValidator.createUser, userController.createUser);
router.post('/login', userValidator.loginUser, userController.loginUser);

module.exports = router;
userController.js(Co
javascript
Copier le code
const userService = require('../services/userService');

exports.createUser = async (req, res) => {
  try {
    
    cons
const user = await userService.createUser(req.body);
    res.status(201).json({ user });
  } catch (error) {
    res.status(400).json({ message: error.message });
  }
};

exports.loginUser = async (req, res) => {
  try {
    const token = await userService.loginUser(req.body);
    res.status(200).json({ token });
  } catch (error) {
    res.status(400).json({ message: error.message });
  }
};
userService.js(Service)
javascript

Copier le code
const User = require('../models/userModel');

con
const bcrypt = require('bcrypt');
const jwt = require('jsonwebtoken');

exports.createUser = async (data) => {
  const { username, password } = data;
  
  con
const hashedPassword = await bcrypt.hash(password, 10);
  
  c
const user = new User({ username, password: hashedPassword });
  await user.save();
  return user;
};

exports.loginUser = async (data) => {
  const { username, password } = data;
  const user = await User.findOne({ username });
  
  if (!user || !await bcrypt.compare(password, user.password)) {
    throw new Error('Invalid credentials');
  }
  
  const token = jwt.sign({ userId: user._id }, process.env.JWT_SECRET, { expiresIn: '1h' });
  return token;
};
userValidator.js(Val
javascript

Copier le code
const { body, validationResult } = require('express-validator');

exports.createUser = [
  body('username').isString().notEmpty(),
  body('password').isLength({ min: 6 }).withMessage('Password must be at least 6 characters long'),
  
  (req, res, next) => {
    const errors = validationResult(req);
    if (!errors.isEmpty()) {
      return res.status(400).json({ errors: errors.array() });
    }
    next();
  }
];

exports.loginUser = [
  body('username').isString().notEmpty(),
  body('password').isString().notEmpty(),
  
  (req, res, next) => {
    const errors = validationResult(req);
    if (!errors.isEmpty()) {
      return res.status(400).json({ errors: errors.array() });
    }
    next();
  }
];
