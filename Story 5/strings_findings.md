Analyse de Sécurité : strings_findings.md

Tableau des vulnérabilités identifiées

google_api_key: AIzaSyBTgztvImsUfMWDa41PCrDWAj7dmyIDhUg
Exploitation financière & Quotas. Utilisation frauduleuse des services Google Cloud facturés au client si la clé n'est pas restreinte par empreinte SHA-1.

firebase_database_url: https://application-client-nickel.firebaseio.com
Exfiltration de données. Point d'entrée direct vers la base de données. Risque critique si les "Security Rules" Firebase sont mal configurées (lecture/écriture publique).

ACCOUNT_ENDPOINT: https://api.nickel.eu/customer-banking-api
Reconnaissance d'infrastructure. Divulgue l'architecture des APIs privées, facilitant les attaques ciblées de type Force Brute ou Déni de Service (DoS) sur l'authentification.

PUSHWOOSH_APPID: DDF11-D1BF9	
Usurpation de Notifications. Permet à un tiers de détourner le service de push pour envoyer des messages de phishing directement aux utilisateurs de l'application.

ENVIRONMENT: production	
Fuite de contexte. Confirme que l'APK cible l'environnement réel. Utile pour un attaquant pour valider qu'il travaille sur des données sensibles et non de test.