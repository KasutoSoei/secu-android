STORY 7



Pour cette story il fallait recompiler l'apk après avoir identifié des vulnérabilités et mauvaises pratiques dans le bytecode décompilé. 
Pour cela nous avons utilisé à nouveau apktool, mais cette fois avec la commande suivante :

apktool b app_src

Où app_source est le dossier source correspondant à l'APK décompilé.

Cela créer un dossier dist dans app_src, contenant l'APK recompilé à l'intérieur.