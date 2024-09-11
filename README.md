# PRACTICA-2
## Integrantes
-Luis Eduardo Mariscal Ceja

-Jarhim Salvador Pahua Leyva

-Dafne Stephany García García

## Introducción
En la práctica 2, se programa el brazo para realizar una tarea que permite manipular objetos. El proceso incluye enseñar posiciones al robot usando el comando TEACH, etiquetar (label) puntos clave para referencia,así como la configuración del HOME  y luego escribir el código en el bloque MAIN para mover un fusible desde una ubicación inicial hasta una caja. La práctica refuerza habilidades de programación, control de movimientos y uso de comandos básicos del software Epson RC+.

El MAIN es el bloque principal de código donde se escribe la lógica central de un programa que controla el robot. Es el punto de inicio de la ejecución del programa y generalmente contiene todas las secuencias o comandos que se quieren ejecutar. En el MAIN  se pueden llamar a subrutinas, funciones, y también se pueden incluir comandos como GO y HOME

El comando GO se usa para mover el robot a una posición específica predefinida. Estas posiciones pueden ser absolutas o relativas, y se definen en el entorno del programa antes de que el comando GO sea ejecutado. En el caso del brazo utilizamos la salida 2 con ON y OFF para abrir y cerrar la pinza que sostiene el fusible.

El comando HOME lleva al robot a su posición de referencia o posición de inicio. Normalmente, el robot tiene una posición de HOME que se establece al encender el robot o cuando se calibra.
El modo JOINT y el modo WORLD son dos formas de controlar el movimiento de un brazo robótico, y cada uno tiene su enfoque dependiendo del tipo de tarea.
En el modo JOINT, el movimiento se controla directamente en las articulaciones del robot, el modo WORLD (también conocido como cartesiano) permite mover el brazo del robot en coordenadas X, Y, Z dentro de un espacio global. Este modo fue el que más se utilizó para guardar los puntos a programar.

## Instrucciones
Primeramente, se abrió el software de simulación y control del brazo robótico EPSON RC, para posteriormente abrir el simulador en la pestaña de tools con robot manager y el simulator(como se meustra en la imagen 1), es importante mencionar qur antes de esto tenemos que definir la conexión C4 sample como se hizo en la práctica 1.
![image](https://github.com/user-attachments/assets/de88c743-8a49-48e3-9d0c-ef1fe6c0de0d)
Imagen 1

En Robot manager se entra al apartado de HOME CONF , mandando a -90 grados el J5 (como se muestra en la imagen 2), que es de donde el robot va a partir.
![image](https://github.com/user-attachments/assets/be6ef098-7b7d-46a4-9632-e689304a5400)
Imagen 2

Luego, se selecciona el apartado de JOG AND TEACH en robot manager y ya ahí, se van a definir las posiciones que se van a definir mediante el modo world (mediante coordenadas x, y,z), como se meustra en la imagen 3.
![image](https://github.com/user-attachments/assets/02849d94-4b9d-48fb-a0ff-2bd61b5708d8)
Imagen 3

Una vez definida la posición deseada, se pasa a seleccionar la función de teach en donde se nombra el punto a definir (imagen 4)
![image](https://github.com/user-attachments/assets/7a00edf0-d357-4b0d-a97a-96d3e04b2019)
Imagen 4

Este paso se repitió según las necesidades para que el brazo fuera capaz de recoger la pieza de un punto para dejarla en otro, en donde dos de los integrantes del equipo iban observando cual sería la posición mejor para que el integrante restante fuera moviendo mediante coordenadas las posiciones.

Una vez definidos todos los puntos deseados, se entró al Main mediante el apartado de program files ubicado en la parte izquierda de la interfaz como se meustra en la imagen 5, en donde se sigue la siguiente secuencia:

-Home: Punto inicial
- Punto 1: El brazo se dirige justo a la posición previa a recoger la pieza para abrir la pinza.
- Punto 2: La pinza agarra la pieza.
- Punto 3: Donde la pinza deja la pieza en la posición final.

![image](https://github.com/user-attachments/assets/5608789f-57b4-4116-b975-a21867d8c96f)
Imagen 5

Algo importante a mencionar es que se debe regresar al punto 1 antes de ir a Home para ir al punto 3, debido a que si no se hace de esta manera el Brazo choca con la base.

Nota: Para accionar la pinza, la herramienta desiganda es la 2, por lo tanto para abrirla se usó el comando "on 2" y para cerrar "off 2".
Nota 2: Para conectar al brazo robótico se selecciona la sonexión a USB (imagen 6).
Nota 3: El botón negro es de paro de emergencia y el botón verde es para un reset, ambos se utilizaron para poder conectar el software con el brazo robótico, debido a que previo a esto el mismo se encontraba en paro de emergencia, cosa que se ppudo visualizar en el semáforo debido a que se encontraba parpadeando.

![image](https://github.com/user-attachments/assets/962abb15-f146-4701-8a0a-a18ef229f850)
Imagen 6

## Conclusiones
- Luis Eduardo Mariscal Ceja:
En la práctica 2 se  aplicó programación y manipulación de robots industriales a través del uso del software Epson RC+. Se programa el brazo robótico para realizar una tarea específica de manipulación de objetos, que incluye mover un fusible desde una posición inicial hasta una caja. Para lograr esto, se enseñan posiciones al robot mediante el comando TEACH, se etiquetan puntos clave con label y se configura la posición de inicio mediante el comando HOME. Posteriormente, en el bloque MAIN, que es el núcleo del programa, se escriben las secuencias lógicas que permiten ejecutar los movimientos del robot. En el MAIN se incluyen comandos como GO, que mueve el robot a posiciones predefinidas, y HOME, que lleva al robot a su posición de referencia. Durante la programación, se utilizó la salida 2 con ON y OFF para abrir y cerrar la pinza que sostiene el fusible.
Además, se exploraron dos modos de control de movimiento del brazo robótico: modo Joint y modo World. En el modo Joint, se controlan directamente las articulaciones del robot, permitiendo movimientos más fluidos, mientras que el modo World, también conocido como cartesiano, permite mover el brazo en coordenadas X, Y, Z. Para la práctica, el modo World fue el más utilizado para guardar y ejecutar los puntos de movimiento programados.

- Jarhim Salvador Pahua Leyva:
Para llevar a cabo la práctica 2 es importante mencionar que se debe tener previo conocimiento de la interfaz del software Epson RC+. Para comenzar se configuró el punto “Home” mediante el modo World, definiendo J5 en -90. Para esto se configuraron los pasos en long, y al tener una ligera diferencia se configura el paso con esa diferencia. Ya configurada la posición de “Home” se pasó a definir los puntos necesarios para realizar la rutina que tomará una pieza para moverla a otro lado, donde se tuvieron que tener consideraciones para que el brazo robótico no chocará con los demás componentes dentro de la cabina. Finalmente, ya definidos los pasos necesarios, la rutina se define en la ventana de Main.prg, donde se utiliza el comando “Go” para ir a un punto definido,  “Home” para ir al punto inicial, “On 2” y “Off  2” par abrir y cerrar la pinza respectivamente. 

- Dafne Stephany García García:
En la presente práctica se aprendió el uso de la programación del brazo robótico mediante el software EPSON RC+, en donde se se vió como es que en la industria se programan los movimientos continuos que tendrá un robot para que un operador no lo tenga que estar manejando en tiempo real, si no, que el brazo mismo trabaje de manera automatizada. Es importante mencionar que la programación de los movimientos debe ser exacta y precisa, debido a que si no lo es y hay un choque con algún objeto el mecanismo del brazo es detenerse como en modo paro de emergencia. 

## Referencias bibliográficos
[1] (S/f). Epson.com. Recuperado el 11 de septiembre de 2024, de https://files.support.epson.com/far/docs/epson_rc_express_rev.3__es_cpd61549_(spanish).pdf


