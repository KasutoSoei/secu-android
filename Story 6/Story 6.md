STORY 5 : 


En parcourant le code, la première chose qui saute aux yeux c'est l'obfuscation assez poussée : 
* les noms de variables, classes et méthodes sont remplacés par des lettres (a, b, c) ou des noms type zzg, zzh. C'est une bonne pratique pour ralentir le reverse-engineering, mais ça montre aussi que les développeurs sont conscients que l'APK peut être décompilé.
Malgré ça, en regardant la classe BuildConfig, on tombe sur un gros problème : toute la configuration sensible est écrite en dur directement dans le code. On retrouve les URLs des APIs internes (customer-banking-api, customer-authentication-api, personal-space-api), l'identifiant Pushwoosh pour les notifications, le numéro de projet GCM, et surtout la confirmation que c'est bien l'environnement de production. Concrètement, n'importe qui qui décompile l'APK a accès à toute l'architecture backend de Nickel, ce qui facilite énormément le travail d'un attaquant pour préparer des requêtes malveillantes ou du phishing.
Pour corriger ça, il faudrait externaliser ces configurations côté serveur, renforcer les mécanismes d'authentification et restreindre les accès aux APIs côté backend.