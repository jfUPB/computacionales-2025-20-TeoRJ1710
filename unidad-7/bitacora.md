# Bitácora de aprendizaje de la unidad 7

## Actividad 01

🧐🧪✍️ Reporta en tu bitácora

1: Incluye una captura de pantalla del ejemplo funcionando en tu máquina.
<img width="1904" height="1069" alt="image" src="https://github.com/user-attachments/assets/ac6d7016-c7c2-496e-b713-37867dd68740" />


2: Observa el proyecto, trata de entenderlo, pero ten presente que lo analizaremos más adelante.

lo que entiendo es que es una figura GEOMETRICA DE UN TRIANGULO QUEEN FUNCION DE LOS BORDES DE LA VENTANA QUE SE PUEDEN MANIPULAR POR MEDIO DE AGRANDARLAS O ACHICARLAS SE LE PUEDO DAR FORMA AL CUADRADO DE LA VENTANA DE FORMA QUE DE ACUERDO A ESO EL TRIANGULO TAMBIEN CAMBIA.

3: ¿Qué preguntas te surgen al ver el código?. Anota al menos tres preguntas que te gustaría investigar más adelante (no te preocupes que la idea de esta unidad es que las resuelvas).

- Como interactua el triangulo con el tamaño de nuestra ventana
  
- que hace el codigo para que esto se cumpla
  
- como reconoce el triangulo el tamaño de nuestra ventana

  ## Actividasd 02

  🧐🧪✍️ Reporta en tu bitácora

Necesito que hagas digestión de esta información y que la entiendas. Para ello te voy a pedir un resumen en tus propias palabras de lo que acabas de leer. En tu resumen debes tratar de conectar GLFW, opengl32.lib, GLAD, GLM y los drivers de la GPU. ¿Qué rol cumple cada uno? ¿Cómo se relacionan entre sí? Mira, trata de hacer esto de memoria y como si estuvieras contándole a un amigo que quiere aprender OpenGL. Cuando haces el proceso de memoria tu cerebro hace un esfuerzo adicional y eso te ayuda a aprender. Además, si no recuerdas algo quiere decir que no lo entendiste bien y eso es una buena señal para que vuelvas a leerlo.

R: Bueno al leerlo todo y mas o menos entenderlo y intentando recordar puedo decir con mis propias palabras es que primero las funciones de cada uno, GLFW es el que se encarga de las funciones de manejar evento y ventanas, osea el contexto, GlAD de encarga del mejor procesamiento de las funciones de opengl, opengl32 permite la creacion del contextop iniial para Opengl y GLM por lo que entiendo es lo  de glm_101, y los frivers de mi tarjeta grafica es en donde esta implementadas las funsiones de opengl 4.6 y mas especifica conexion con glad que recuerdo que ayuda a la mejor procesamiento de las funciones la cual las leee de los drivers de la tarjeta grafica

## Actividad 03

🧐🧪✍️ Reporta en tu bitácora

Qué tal si ensayas. Prueba con esta línea

// 9) Configura el viewport
glViewport(0, 0, bufferWidth, bufferHeight);

¿Qué pasa si?

glViewport(0, bufferHeight/2, bufferWidth/2, bufferHeight/2);

Cambia los valores de bufferWidth y bufferHeight: divide por 2, por 4, multiplica por 2, por 4, etc. ¿Qué pasa? ¿Qué observas? ¿Qué crees que está pasando?

R:

A simple vista puedo ver el triangulo en si como casi en la misma forma que el anterior peero un poco mas angosto

<img width="1919" height="1070" alt="image" src="https://github.com/user-attachments/assets/33511cce-7d52-467f-99b3-270e8a83d1b3" />

pero al principio vi que el triangulo aparecio en la esquina de la pantalla lo cual se me hizo bastante raro

lo que creo que esta pasando es que al dividir sus medidas su forma cambia por eso veo que se ve mas angosto

y si lo multiplico or regla de 3 deberia de verse mas ancho

No pues no se puso mas ancho y lo intente hasta por 8

entonces debe de ser al inicio de la aplicacion porque lo unico que observo por ejemplo cuando lo dividi por 8 me salio el triangulo pero chiquito en la esquina de la pantalla.

entonces por lo del viewport no debe de estar bien ajustado y por eso aparece como en una esquina




🧐🧪✍️ Reporta en tu bitácora

Ya llevas un rato leyendo y no has hecho digestión. Para favorecer tu aprendizaje, es necesario que te detengas un momento y ELABORES lo que has visto hasta ahora. Mira, quiero contarte algo. Lo que he venido haciendo de manera implícita en el curso es enseñarte a aprender a aprender. ¿Te has dado cuenta? Te voy exponiendo a conceptos y luego te pido que experimentes, que los pongas en práctica, que los reflexiones. Entonces, no te quedes largos periodos de tiempo leyendo, viendo tutoriales o escuchando. Cada cierta cantidad de tiempo, puede ser cada 30 minutos o cada hora, haz una pausa y reflexiona sobre lo que has aprendido.

¿Cómo lo haces? Realiza un resumen de lo que has aprendido hasta ahora, haciendo un diagrama conceptual o un mapa mental. Experimentando. ¿Cómo? Haciendo la pregunta mágica: ¿Qué pasaría si? ¿Qué pasaría si cambio el tamaño de la ventana? ¿Qué pasaría si cambio el tamaño del viewport?

Entonces hagamos “digestión”: en tu bitácora, escribe un resumen de lo que has aprendido hasta ahora y piensa en un experimento del tipo ¿Qué pasaría si?

R:

Bueno la verdad hasta ahora he aprendido no mucho del funcionanmiento de como funciona en si el codigo pero si de los mas basico del opengl, de sus componentes y lo que lo hace funcionar como el glad o el glm, tambien he aprendido solamente visualmente como se comporta el triangulo y que hace si le cambiamos de tamaño la pantalla, tambien que es en si lo que dibuja lo que estamos viendo y como se da ese procedimiento como por ejemplo que no sabia que en realidad el opengl era el que ordenaba a la gpu que dibujar y como hacerlo y mas cosas

y la verdad me gustaria saber que pasaria si presiono f11 mientras tengo la pantalla completa, cambiara de tamaño ? o se mantendra como se muestra cuando hacemos click en el icono para ponerlo de pantala completa


🧐🧪✍️ Reporta en tu bitácora

¿Qué pasa si cambias el primer parámetro de glDrawArrays a GL_LINES? ¿Qué pasa si lo cambias a GL_POINTS? ¿Qué pasa si cambias el tercer parámetro a 2? ¿Qué pasa si lo cambias a 4?

En esta unidad no profundizaremos en los tipos de primitivas, pero es importante que entiendas que OpenGL puede dibujar diferentes tipos de primitivas (triángulos, líneas, puntos, etc.).

R:

Pas que al cambiarlo evidentemente se dicuja una linea

<img width="396" height="440" alt="image" src="https://github.com/user-attachments/assets/d00bb0b6-b1da-4fbc-ac2a-4767d375712f" />

y si lo cambio a gl points 

<img width="390" height="428" alt="image" src="https://github.com/user-attachments/assets/1ee13252-7c85-4ec1-bedf-243d21d08a10" />

se alcanza a ver un pequeño punto

y si cambio los parametros pasa que

que cuando lo cambie a 2 no aparecio nada y no se porque, y si lo pongo en 4 aaprece esto

<img width="1918" height="1079" alt="image" src="https://github.com/user-attachments/assets/d0830fe0-c2aa-423a-b309-f1b19e5027b8" />

osea que cuando le asignamos menos vertices de los que necestia la figura directamente no lo dibuja. 

🧐🧪✍️ Reporta en tu bitácora

Vamos a terminar esta actividad con un nuevo momento de consolidación parcial. Hay algunos conceptos relacionados con los shaders y el pipeline de OpenGL que no hemos visto en detalle, pero no te preocupes, los vamos a trabajar en la siguiente actividad. Por ahora, quiero que te concentres en lo que has aprendido hasta aquí. Explica con tus propias palabras los siguientes conceptos. Puedes usar ejemplos, analogías o diagramas para ilustrar tus respuestas. Es importante que intentes responder estos conceptos sin ver inicialmente tus notas. Trata de ejercitar tu memoria y tu comprensión. Luego, puedes revisar tus notas para completar o corregir lo que hayas escrito.

¿Qué es el contexto OpenGL?

R:

Un contexto OpenGL es una estructura de datos interna que contiene El estado de opengl como sahders buffers, la version de opengl, la concexion o el lienzo en donde se va a dibujar los graficos en la ventana, los recursos y lo que se vaya a usar

¿Cuál es el rol de la biblioteca GLFW y qué ventaja tiene usarla?

R: tiene la ventaja que permite abrir ventanas y es la que nos permite manejar diferentes tipos de eventos como el reton o el teclado, etc

¿Por qué crees que OpenGL necesita un contexto (recuerda la analogía del taller de arte)?

R: Pues digammos que opengl es un perfecto artista con todas las habilidades, pero si no se le da un contexto ni un lienso ni un pinsel ni una idea de que dibujar va ser inutil, es necesario brindar el contexto para que opengl sepa con que trabajar, que hacer y pues su version.

¿En últimas qué será el framebuffer y a qué te recuerda de las dos primeras unidades del curso?

R:
Me recuerda mucho si me baso en las primeras semanas del curso como la herramienta que utilizamos para aprender todo esto de la memoria y los datos que almacena, me recuerda mcucho al ejercicio que hicimos de dibujar una linea que se iba desplazando asi que me imagino que tiene similitud aunque ahora no me acuerdo muy bien

¿Qué relación entre en el viewport y el framebuffer?

R: que el viewport indica al framebuffer en que parte dibujar como la resolucion de la ventana que tanto dibujar, etc.

¿En todo la analizado hasta ahora qué rol juega los drivers de la GPU y la GPU misma?

R: 
La GPU es en si el artista que dibuja y opengl es el que le indica que dibujar mediante la memoria de la gpu


¿Por qué crees que sea necesario activar el VSync? ¿Si no lo activas y la imagen es estática qué crees que pase, y si es dinámica?

R:
en si el vsync es para que la gpu se alinee con la frecuencia de dibujado del monitor o de la pantalla de la maquina

y si no se activa pues me ha pasado en varios videojuegos que la imangen se puede ver muy rara como con errores en el dibujado
eso ya lo busque y se llama tearing, y si esta estatica pues no se nota, pero ne movimiento se ven los mismos erores y se ve horrible, por eso es que se active para que se vea fluido

En esta unidad estamos usando OpenGL moderno, pero ¿Qué es OpenGL Legacy? ¿Qué diferencias hay entre ambos?

R: 
Open legacy como dice su nombre es una version vieja y todo era muy directo y tosco, el programador no tenia taanto control sobre lo que queria dibujar, y en la actual se pueden usar vuffers y shaders y es mas controlable 

¿Qué es el shader program? ¿Por qué es importante en OpenGL moderno?

R:
Hacen parte de opengl y ayudan a darle ordenes a la gpu de como pintar ciertas cosas como pixeles o lineas, etc

Trata de revisar el código setupTriangle(), intuitivamente ¿Qué crees que hace? ¿Qué crees que es el VAO y el VBO?
R: pues lo que puedo decir es que VAO es como el orden en como opengl debe de leer los datos y VBO es como en donde esta el triangulo o como debe dibujarlo
osea es como que una son las indicaciones y otro es como usarlo

En el ciclo principal (game loop) de OpenGL, notaste que en cada frame (cuadro) le decimos a openGL que use el shader program y el VAO. Si le indicas esto antes del game loop ¿Será necesario seguirlo haciendo en cada loop? Si no es necesario ¿En qué casos crees que esto puede ser útil?

R:
No, porque ya le estas indicando esa informacion antes del loop osea que en cada loop la debe der estar usando, aunque si necesitamos usar varias figuras ahi si es necesario indicarlo en cada loop, y puede ser util cuando solo se tiene una figura

Finalmente, recuerda lo que hace glfwSwapBuffers(mainWindow); ¿Por qué crees que es importante? ¿Qué pasaría si no lo llamas? ¿Cómo explicas lo que pasa si no lo llamas? (experimenta)

Pues por lo que pude ver a pesar que la imagen es estatica despues de indagar un poco pues en si en pocas paabras es lo que actualiza la pantalla, osea que si no lo llamamos pintamos el lienso una vez y ya, no hya mas y no hay actualizaciones oseas que la imagen se queda estatica.

R:

## Actividad 04

🧐✍️ Reporta en tu bitácora

Luego de estudiar las unidades 1 y 2 de este curso y ver el video, escribe con tus propias palabras ¿Cuál es la diferencia entre una CPU y una GPU?

🧐✍️ Reporta en tu bitácora

Es momento de practicar la técnica de aprender a aprender que te he venido mostrando de manera insistente a lo largo del curso. Te voy a proponer una serie de preguntas para que reflexiones y escribas en tu bitácora. Trata de responder de memoria a cada pregunta. No busques la respuesta en el video. Trata de recordar lo que viste. De todas maneras si no lo logras hacer, regresa al video y busca la respuesta.

¿Cuáles son los tres pasos claves del pipeline de OpenGL? Explica en tus propias palabras cuál es el objetivo de cada paso.
La gran novedad que introduce OpenGL moderno es el pipeline programable. ¿Qué significa esto? ¿Qué diferencia hay entre el pipeline fijo y el programable? ¿Qué ventajas le ves a esto? y si el pipeline es programable, ¿Qué tengo que programar?
Si fueras a describir el proceso de rasterización ¿Qué dirías?
¿Qué son los fragmentos? ¿Es lo mismo un fragmento que un pixel? ¿Por qué?
Explica qué problema resuelve el Z-buffer y ¿Qué es el depth test?
¿Por qué se presenta el problema de la aliasing? ¿Qué es el anti-aliasing?
¿Qué relación hay entre la iluminación y el fragment shader? Siempre es necesario tener en cuenta la iluminación en un fragment shader? o puedo hacer un fragment shader sin iluminación? Explica que implicaciones tiene esto.
¿Qué implica para la GPU que una aplicación tenga múltiples fuentes de iluminación?


🧐🧪✍️ Reporta en tu bitácora

Modifica el código del triángulo para que sea interactivo.
Incluye una captura de pantalla del triángulo interactivo funcionando en tu máquina.
Explica el proceso de normalización de las coordenadas del mouse y cómo se relaciona con el sistema de coordenadas de OpenGL.
Explica el proceso de normalización a coordenadas de dispositivo (NDC) y cómo se relaciona con el sistema de coordenadas de OpenGL.


## Actividad 05

🧐🧪✍️ Reporta en tu bitácora

Modifica el código del triángulo para que sea interactivo.
Incluye una captura de pantalla del triángulo interactivo funcionando en tu máquina.
Explica el proceso de normalización de las coordenadas del mouse y cómo se relaciona con el sistema de coordenadas de OpenGL.
Explica el proceso de normalización a coordenadas de dispositivo (NDC) y cómo se relaciona con el sistema de coordenadas de OpenGL.
