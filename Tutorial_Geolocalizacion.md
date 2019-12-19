## TUTORIAL PARA LA GEOLOCALIZACIÓN

1-.En Android Studio creamos un proyecto nuevo vacio

![](.Tutorial_Geolocalizacion_images/df2ac5dc.png)
![](.Tutorial_Geolocalizacion_images/b67ad832.png)

2-.Dentro del Gradle Scripts, en la parte de build.gradle anexamos las siguientes dependencias en la parte correspondiente:

![](.Tutorial_Geolocalizacion_images/3eb5110a.png)

Debemos de verificar que la implementación play-services-maps y la play-services-location deben coincidir en la versión, es decir "16.0.0" 

3-.Ahora en la carpeta "manifest" vamos a agregar las siguientes dependencias:

![](.Tutorial_Geolocalizacion_images/e057f38e.png)   

De las cuatro dependencias las mas importantes son : "android.permission.ACCESS_COARSE_LOCATION" y "android.permission.ACCESS_FINE_LOCATION" donde éste segundo es para el GPS.

4-.Vamos ahora a crear una clave de los mapas, esto nos servirá para que se pueda visualizar el mapa y de nuestra ubicación en tiempo real. Nos vamos a la carpeta "app/new/Google/Google Maps Activity"

![](.Tutorial_Geolocalizacion_images/874b8a9c.png)

5-.Para que podamos hacer uso del Google maps, debemos autenticarnos con nuestra cuenta de gmail. Nos posicionamos en la carpeta "values", ingresamos al archivo google_maps_api.xml y copiamos la liga que nos aparece en esta clase para pegarla en un navegador.

![](.Tutorial_Geolocalizacion_images/c1f3ffa9.png)

![](.Tutorial_Geolocalizacion_images/0706fb10.png)

6-.Una vez que pegamos esa liga en el navegador nos aparece la siguiente pantalla para registrar la aplicación para utilizar Maps SDK, aceptando las condiciones.

![](.Tutorial_Geolocalizacion_images/6e26b5f7.png)

7-.Una vez que aceptemos las condiciones de uso, nos genera una Clave de API, la cual debemos copiar pues la pegaremos en la clase google_maps_api.xml

![](.Tutorial_Geolocalizacion_images/63bd6319.png)

![](.Tutorial_Geolocalizacion_images/1c22f048.png)

Es importante indicar que no debemos seleccionar la opción de "Restringir Clave" ya que ésto nos deshabilitará constantemente el uso de mapas.

8-.La clave que nos proporcionó la copiamos y la pegamos en "MapsActivity" en la parte que se indica subrayado en amarillo.

![](.Tutorial_Geolocalizacion_images/206c5bf3.png)

9-.Ingresamos a la clase "MapsActivity" el cual se generó cuando creamos "app/new/Google/Google Maps Activity". Esta clase es la más importante con la que se trabajará. Inicialmente se herada la clase AppCompatAActivity que de ahi se heredan todas las clases, además que implementamos 4 interfaces.

![](.Tutorial_Geolocalizacion_images/bac5347b.png)

![](.Tutorial_Geolocalizacion_images/e7a8805d.png)

10-.La primer interfaz es "OnMapReadyCallback" la cual nos indica que una vez que se descargue el mapa podamos acceder al Googlemap que es el que se mostrará.

![](.Tutorial_Geolocalizacion_images/ae041b1d.png)

11-.La segunda interfaz es "GoogleApiClient.ConnectionCallbacks" indica que hay un cliente que hace la localización que se activa con el celular una vez que recibe la solicitud, lo que hace en el código es que cuando se tiene conexión da la geolocalización (latitud, longitud, etc)

![](.Tutorial_Geolocalizacion_images/99d2a0ba.png)

12-.La tercer interfaz es "GoogleApiClient.OnConnectionFailedListener" la cual nos indicará en caso de que falle la conexión en caso de no tener red y no se pueda realizar la geolocalización.

![](.Tutorial_Geolocalizacion_images/8cc355f0.png)

13-.La cuarta interfaz "LocationListener" es la más importante pues es la que estará mostrando los cambios de la visualización de localización, es un "escuchador" en cuanto a indicar los cambios de ubicación.

![](.Tutorial_Geolocalizacion_images/3f65dba8.png)

14-.Cuando creamos un MapActivity en automático nos genera un "mMap: GoogleMap"

![](.Tutorial_Geolocalizacion_images/26c3928f.png)

15-. Tenemos que declarar el Método "setUpGCliente()" , lo colocamos inmediatamente despues de ver el fragmento que inicializa el mapa.

![](.Tutorial_Geolocalizacion_images/a23c4115.png)

16-.La función onMapReady nos la implementa por default al crear el MapActivity.

![](.Tutorial_Geolocalizacion_images/5fa5e89a.png)

17-.Modificamos las coordenadas en la ubicación que nos da por default y colocamos las coordenadas en las que nos ubicamos.

![](.Tutorial_Geolocalizacion_images/af32c74c.png)

18-.Configuramos el punto que se visulizará en el mapa el cual nos mostrará nuestra ubicación.

![](.Tutorial_Geolocalizacion_images/55a5f9bc.png)

19-.Colocamos @Synchronized el cual hará que se repita cada determinado tiempo. Generamos un objeto "builder" de la clase GoogleApiClient , el cual el objeto builder inicializa la activity MapActivity para que nos podamos conectarnos a la api de Geolocalización, "this" hace referencia a ésta activity en la que estamos.

![](.Tutorial_Geolocalizacion_images/757e333a.png)

20-.A continuación habilitamos la autoadministración de la activity para que el gps del celular se active de manera automática sin necesidad de activarlo de forma manual,por lo que con el método "setUpGClient" se hará la activación de forma automática.

![](.Tutorial_Geolocalizacion_images/a0a92609.png)

21-.Con el método "addConnectionCallbacks" el cual invoca las llamadas a la conexión para saber si esta disponible para la localización y el "addOnConnectionFailedListener" nos indicará si hay alguna falla en la conexión.

![](.Tutorial_Geolocalizacion_images/8d57c00d.png)

22-.El "addApi(LocationServices.API)" es la clase que nos va a dar la geolocalización y ubicación actual y con el googleApiClient procedemos a conectarnos.

![](.Tutorial_Geolocalizacion_images/7540251b.png)

![](.Tutorial_Geolocalizacion_images/8562408b.png)

23-.A continuación invocamos un método llamado "onLocationChanged" el cual nos va a ayudar a detectar cuando cambiamos de ubicación y recibe de argumentos un objeto de tipo location.

![](.Tutorial_Geolocalizacion_images/831af4ac.png)

24-.Inicializamos mylocation, indicando que el argumento que se le va a pasar es el que se va a activar.

![](.Tutorial_Geolocalizacion_images/08710cc3.png)

25-.Inicializamos la localización "mylocation" con la latitud y longitud.

![](.Tutorial_Geolocalizacion_images/3ee6ab97.png)

26-.Cuando se cambie la localización le indicamos al mapa que con la cámara a nuestra variable "syndey" que es de nuestra ubicación.

![](.Tutorial_Geolocalizacion_images/0782c848.png)

27-.El método "onConnected" es de suma importancia ya que cuando se corra la aplicación éste metodo se activa y lo que hace es que automaticamente checa los permisos del GPS, ya que enciende el GPS como si se activara de forma manual.

![](.Tutorial_Geolocalizacion_images/298d3886.png)
![](.Tutorial_Geolocalizacion_images/cccea00d.png)

28-.Con la clase ContexCompact indicamos que autocheque los permisos en el contexto del MapsActivity.

![](.Tutorial_Geolocalizacion_images/bff8f71c.png)

29-.En el segundo argumento le indicamos que nos vamos a meter en el archivo "android manifest" y vamos a encender el GPS.

![](.Tutorial_Geolocalizacion_images/e7c370c0.png)

30-.Hacemos la búsqueda de todos los permisos

![](.Tutorial_Geolocalizacion_images/e1e525fb.png)

31-.De todos los permisos que se encuentran, si el permiso de localización NO está habilitado entonces que enliste el permiso de localización y lo agregue al Manifiesto si es que el GPS esta APAGADO.

![](.Tutorial_Geolocalizacion_images/e4ac41c3.png)

32-.Ahora si los permisos que se necesitan están vacios, que pida el permiso y que lo habilite.

![](.Tutorial_Geolocalizacion_images/0cf2f2e1.png)

33-.En cuanto cheque los persmisos que nos envíe la localización.

![](.Tutorial_Geolocalizacion_images/dc3b51e7.png)

34-.El método "onRequestPermissionsResult" se activa despues de haberse activado el método checkPermissions. Una traducción rápida de éste método diría una vez que se dió el permiso dependiendo del resultado en el manifiesto se agrega y activamos lo que es la autorización y nuevamente activamos la localización en caso de que el usuario este cambiando de ubicación.

![](.Tutorial_Geolocalizacion_images/b06ac1a0.png)
![](.Tutorial_Geolocalizacion_images/1dbfd029.png)

35-.Las siguientes partes de código son los permisos que están en hexadecimales y sirven para que cargue el número del permiso.

![](.Tutorial_Geolocalizacion_images/521f9163.png)

36-.El método "getMyLocation" es de suma importancia, colocamos el @@SuppressLintel cual nos ayudará a saber si ya se solicitó los permisos y en caso de no haberlos solicitado nos marcaría error. Cuando ejecutamos la aplicación nos envía un mensaje preguntando si queremos que acceda a nuestra ubicación , éste método es el que solicita ese permiso.

![](.Tutorial_Geolocalizacion_images/830a5c70.png)

37-.Declaramos una variable que se llama "locationRequest" que es como una petición de la localización, con la clase "locationRequest" lo activamos.

![](.Tutorial_Geolocalizacion_images/e4b899d0.png)

38-.El objeto locationRequest invocamos su atributo intervalo el cual nos indicará cada cuanto tiempo se conectará al GPS y actualizará el Mapa, en éste caso será cada 3 segundo. Además le damos una PRIORIDAD la cual será ALTA para que nos de la ubicación lo más preciso.

![](.Tutorial_Geolocalizacion_images/e967f1ba.png)

39-.La siguiente parte del código es para activar los servicios de geolocalización.

![](.Tutorial_Geolocalizacion_images/f0c84f46.png)

40-.El método "onActivityResult" después de que acabe el activity nos da nuestra localización, El RESULT_OK -> getMyLocation() es en caso de aceptar que la aplicación muestre nuestra ubicación, el RESULT_CANCELED -> finish() se cerrará en caso de que de niegue el permiso a nuestra ubicación.

![](.Tutorial_Geolocalizacion_images/6066bb23.png)





                                                                                      