Commande pour générer une clé :

keytool -genkey -v -keystore ma-cle-securite.keystore -alias mon_alias -keyalg RSA -keysize 2048 -validity 10000
Mot de passe clé : Key1234

Commande pour signer l'apk en fonction de la clé généré : 

apksigner sign --keystore ma-cle-securite.keystore --out mon_app_signee.apk mon_app_alignee.apk

Log de la vérification de si la clé est bien signée :

apksigner verify --verbose signed_app.apk

Verifies
Verified using v1 scheme (JAR signing): true
Verified using v2 scheme (APK Signature Scheme v2): true
Verified using v3 scheme (APK Signature Scheme v3): true
Verified using v3.1 scheme (APK Signature Scheme v3.1): false
Verified using v4 scheme (APK Signature Scheme v4): false
Verified for SourceStamp: false
Number of signers: 1