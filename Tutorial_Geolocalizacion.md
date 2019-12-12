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

10




                                                                                      