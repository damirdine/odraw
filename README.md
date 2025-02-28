# Odraw

Odraw est un jeu de positionnement de pixels inspiré du concept de Pixel War.
Les joueurs peuvent collaborer ou s'affronter pour dessiner des images en plaçant des pixels sur une grille partagée en temps réel.

## Fonctionnalités

- 🎨 **Placement de pixels** : Ajoutez des pixels sur une grille partagée.
- 🔄 **Mise à jour en temps réel** : Utilisation des WebSockets pour une synchronisation fluide.
- 📦 **Stack technologique moderne** :
  - Backend : **NestJS** pour une architecture scalable et modulaire.
  - Frontend : **Vue.js** et **React.js** pour une interface utilisateur dynamique.
  - WebSockets : Communication bidirectionnelle en temps réel.
- 🐳 **Dockerisation** : Conteneurisation pour une exécution portable.
- 🚀 **CI/CD** : Pipelines de déploiement automatisés.

## Installation et démarrage

### Prérequis
- [Node.js](https://nodejs.org/) installé
- [Docker](https://www.docker.com/) installé

### Étapes
1. **Cloner le dépôt**
   ```sh
   git clone https://github.com/damirdine/odraw.git
   cd odraw
   ```

2. **Installer les dépendances**
   ```sh
   npm install
   ```

3. **Lancer l'application en mode développement**
   ```sh
   npm run start
   ```

4. **Lancer avec Docker**
   ```sh
   docker-compose up --build
   ```

## Contribution
Les contributions sont les bienvenues ! Ouvrez une issue ou proposez une PR.

## Licence
MIT License - Voir [LICENSE](LICENSE) pour plus de détails.

