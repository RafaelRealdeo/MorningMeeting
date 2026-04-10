
# Morning Meeting

## Vue d'ensemble
"Morning Meeting" est un script d'automatisation robuste conçu pour récupérer et agréger des données financières et macroéconomiques provenant de diverses sources, telles que les indices boursiers, les matières premières et les taux. Le script utilise des API en temps réel, traite les données et fournit des résumés utiles pour aider les utilisateurs à suivre les conditions du marché mondial de manière efficace. Ce projet est basé sur [n8n](https://n8n.io/) pour une automatisation facile et une intégration avec des sources de données externes.

## Fonctionnalités
- Récupère des données en temps réel des principaux indices boursiers, tels que le CAC40, le S&P 500, le Nasdaq, et d'autres.
- Récupère des données économiques comme les taux d'intérêt, les statistiques sur l'inflation et l'emploi.
- Traite les données en temps réel et les agrège en résumés faciles à interpréter.
- Génère automatiquement des e-mails avec des résumés des meilleurs et des pires mouvements du marché.
- Suivi des événements macroéconomiques pour les principaux indicateurs financiers tels que l'IPC, le PIB et les taux d'emploi.

## Instructions d'installation

### Prérequis
Assurez-vous d'avoir les éléments suivants installés :
1. [n8n](https://n8n.io/docs/getting-started/)
2. Node.js (de préférence la dernière version LTS)
3. Identifiants de messagerie (pour l'envoi d'e-mails automatisés)
4. Clés API pour les sources de données financières (comme St. Louis Fed pour l'inflation et le chômage, et d'autres fournisseurs de données de marché)

### Étapes d'installation
1. Clonez le dépôt :
   ```bash
   git clone https://github.com/yourusername/mon-workflow-3.git
   cd mon-workflow-3
   ```

2. Installez les dépendances :
   ```bash
   npm install
   ```

3. Configurez les variables d'environnement :
   - Créez un fichier `.env` dans le répertoire racine et ajoutez les clés API nécessaires et les identifiants de messagerie.
   - Exemple :
     ```
     DATABENTO_API_KEY=your_api_key
     GMAIL_CLIENT_ID=your_gmail_client_id
     GMAIL_CLIENT_SECRET=your_gmail_client_secret
     ```

4. Lancez n8n :
   ```bash
   n8n start
   ```

5. Accédez à l'éditeur n8n à [http://localhost:5678](http://localhost:5678) et chargez votre workflow.

## Utilisation

### Comment fonctionne le Workflow
1. **Déclencheur planifié** : Récupère automatiquement les données à des intervalles spécifiés (par exemple, chaque matin à 9 h).
2. **Récupération des données** :
   - Récupère les données du marché (indices boursiers, matières premières et taux de change).
   - Récupère les indicateurs économiques (inflation aux États-Unis et en UE, données sur l'emploi, etc.).
3. **Traitement des données** :
   - Agrège les données sous une forme résumée pour l'analyse.
   - Applique des transformations de données pour normaliser et nettoyer les données entrantes.
4. **Notification par e-mail** :
   - Envoie un résumé quotidien des meilleurs et des pires mouvements du marché, avec des informations clés sur les tendances du marché.
   - Fournit des informations sur les événements macroéconomiques à venir.

### Exemple de sortie :
- **Top du jour** : 
   - *Entreprise* : Apple Inc.  
   - *Variation* : +1,5%  
   - *Secteur* : Technologie  
   - *Catalyseurs* : Résultats trimestriels solides et lancements de produits.

- **Flop du jour** : 
   - *Entreprise* : Tesla  
   - *Variation* : -3,2%  
   - *Secteur* : Automobile  
   - *Catalyseurs* : Inquiétudes concernant les retards de production et les problèmes de chaîne d'approvisionnement.

- **Calendrier économique** :  
   - Prochain rapport sur l'inflation des États-Unis (données sur l'IPC) à 14 h (EST).

## Contribuer
Les contributions sont les bienvenues ! N'hésitez pas à forker le dépôt, à créer une nouvelle branche et à soumettre une demande de fusion.

### Code de conduite
En participant à ce projet, vous acceptez de respecter le [Code de conduite](./CODE_OF_CONDUCT.md) du projet.

## Licence
Ce projet est sous licence MIT - voir le fichier [LICENSE](./LICENSE) pour plus de détails.

## Remerciements
- [n8n](https://n8n.io/)
- [API Stooq](https://stooq.com/)
- [API ECB](https://www.ecb.europa.eu/stats/eurofxref/eurofxref-daily.xml)
