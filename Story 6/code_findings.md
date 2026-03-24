Vulnérabilités identifiées :

# Mauvaises pratiques :

"class a implements com.pushwoosh.internal.utils.d {
    private String a;
    private String b;
    private String c;
    private String d;
    private String e;
    private Class<?> f;
    private Class<?> g;
    private Class<?> h;
    private boolean i;
    private boolean j;
    private boolean k;
    private int l;
    private int m;
    private final List<Plugin> n = new ArrayList();
    private PluginProvider o;
    ...
}"

"@SafeParcelable.VersionField(id = 1)
    private final int zzg;

    @SafeParcelable.Field(getter = "getErrorCode", id = 2)
    private final int zzh;

    @SafeParcelable.Field(getter = "getResolution", id = 3)
    private final PendingIntent zzi;

    @SafeParcelable.Field(getter = "getErrorMessage", id = 4)
    private final String zzj;"

Appelations de dossiers/fichiers, classes, variables, ... aléatoires. 
-> Rend difficile la compréhension du code et de l'architecture, ainsi que la navigation dans le projet.


# Vulnérabilité :

"public final class BuildConfig {
    public static final String ACCOUNT_ENDPOINT = "https://api.nickel.eu/customer-banking-api";
    public static final String APPLICATION_ID = "com.fpe.comptenickel";
    public static final String BUILD_TYPE = "release";
    public static final String CUSTOMER_AUTHENTICATION_ENDPOINT = "https://api.nickel.eu/customer-authentication-api";
    public static final boolean DEBUG = false;
    public static final String ENVIRONMENT = "production";
    public static final String FLAVOR = "production";
    public static final String GCM_PROJECT_NUMBER = "246766419677";
    public static final String PERSONAL_SPACE_API_ENDPOINT = "https://api.nickel.eu/personal-space-api";
    public static final String PUSHWOOSH_APPID = "DDF11-D1BF9";
    public static final int VERSION_CODE = 150;
    public static final String VERSION_NAME = "2.12.0";
}"

Expositions d'informations sensibles côté client (endpoints, clés, ... en dur et ENVIRONMENT en mode "production").
-> Facilite l'identification de la structure des API, augmente la possibilité d'abus des services (ex : requêtes maveillantes), aide les attaquants à préparer des attaques plus avancées, ...


# Corrections possibles :

- Externaliser la configuration sensible côté serveur
- Utiliser de meilleurs mécanismes d’authentification
- Restreindre l’usage des clés/API côté backend