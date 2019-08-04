# Conectar a wifi desde el terminal

Muchas veces me he visto en la necesidad de conectarme a internet sin entorno gráfico por ejemplo tras  una instalación con el netinstall de Debian ya que uso Openbox y no instalo ningún entorno de escritorio. Os comento esta forma que me parece muy sencilla.
Necesitarás sólo un móvil, yo lo he hecho con mi móvil Android usando la opción Tethering desde el menú de configuración.

Empecemos.
Estamos en un terminal validado con el usuario root.

1. Conectamos el móvil por USB al ordenador.
2. Activamos en el móvil la opción Tethering desde el menú de configuración del móvil.
3. Nos vamos a la consola y escribimos `ip link show` Esto nos mostrará una lista con todas las tarjetas de red de nuestro equipo. Tenemos que buscar la del móvil que tenemos conectado. En mi caso se llama `enp0s20u3` Si lees bien puedes ver si está activa (UP) o no (DOWN)
2. Si la tarjeta de red no está activa, la activamos con `ip link set enp0s20u3 up`
3. Y finalmente hacemos un `dhclient enp0s20u3` para que nos asigne una ip y ya estaremos conectados a internet.

Ojo, te recomiendo que compruebes que el móvil está conectado a tu Wifi por que si está conectado a la red móvil puedes gastar tu tarifa de datos.

Espero que te sea útil.