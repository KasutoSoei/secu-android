STORY 5 : 


L'analyse a révélé 5 éléments sensibles exposés :
* google_api_key (AIzaSyBTgz...) : risque d'exploitation financière si la clé n'est pas restreinte par empreinte SHA-1, un tiers pourrait consommer les quotas Google Cloud facturés au client.
* firebase_database_url (https://application-client-nickel.firebaseio.com) : point d'entrée direct vers la base de données, risque critique d'exfiltration si les Security Rules sont mal configurées.
* ACCOUNT_ENDPOINT (https://api.nickel.eu/customer-banking-api) : divulgue l'architecture des APIs privées, facilitant des attaques brute force ou DoS sur l'authentification.
* PUSHWOOSH_APPID (DDF11-D1BF9) : permet l'usurpation de notifications push pour envoyer du phishing aux utilisateurs.
* ENVIRONMENT: production : confirme que l'APK cible l'environnement réel, validant pour un attaquant qu'il travaille sur des données sensibles.
Le livrable strings_findings.md est fourni avec les extraits et risques associés pour chaque secret identifié.