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

R: El video la verdad ya lo habia visto muchas veces y en temas de la gpu y cpu estoy muy metido porque me encata temas de procesadores y gpu y eso, en si por lo que puedo decir por lo que ya se y por lo que se puede retratar en el video es que se pone a prueba la cpu contra la gpu en temas de imagen en si, vemos que la cpu por asi decirlo en temas de imagen no es algo tan eficiente, aunque en tmas generales de un computador es el cerebro del pc y no hay mas pieza mas importante que el, eso si dejando de lado los procesadores que vienen con graficos integrados, pero que igualmente a comparacion de una gpu la diferencia es enorme, las tarjetas gaficas o gpu son maquinas diseñadas para la imagen el video y la experiencia visual, entonces en terminos generales es eso, no quiere decir que un cpu no se pueda encargar de la imagen, pero la gpu esta diseñada y creada para eso especificamente


🧐✍️ Reporta en tu bitácora

Es momento de practicar la técnica de aprender a aprender que te he venido mostrando de manera insistente a lo largo del curso. Te voy a proponer una serie de preguntas para que reflexiones y escribas en tu bitácora. Trata de responder de memoria a cada pregunta. No busques la respuesta en el video. Trata de recordar lo que viste. De todas maneras si no lo logras hacer, regresa al video y busca la respuesta.

¿Cuáles son los tres pasos claves del pipeline de OpenGL? Explica en tus propias palabras cuál es el objetivo de cada paso.

R: Vertex shaping se encarga en si de la imagen o pues de lo que se va mostrar, osea se encarga de los vertices de los triangulos y como se va mostrar cada cosa, mediante sus cordenadas su posicion o su colocacion, se encarga de mover millones de triangulos y millones de vertcies para poder crear la imagen en si, y porque no digo mostrar, pues porque el mostrar la imagen se encarga el Rasterization que se encarga de mediante los triangulos y lo que se tiene que mostrar con que pixeles de la pantalla mostrarlo, se adapta a la resolucion de pantalla y mediante mas resolucion el proceso se vuleve mucho mas bello porque se puede utilizar mas pixeles para ciertos trianculo y mostrar una imagen mas detallada y definida, la gpu calcula las cordenanadas de cada tringulo y asifna cierta cantidad de ixeles para rellenar ese trianculo seleccionado, y el fragmant shading que ya que la imagen esta ya diseñada y mostrada este se encarga de algo muy importante que es la apariencia de la imagen o mas bien el color, toma en cuenta shaders o cualquier tiempo de iluminacion, textura, color, ect que se haya diseñado y este le da ese tipo de color al pixel para que sea pintado segun lo que se requiera y lo que se diga segun todos los factores ya dichos.


La gran novedad que introduce OpenGL moderno es el pipeline programable. ¿Qué significa esto? ¿Qué diferencia hay entre el pipeline fijo y el programable? ¿Qué ventajas le ves a esto? y si el pipeline es programable, ¿Qué tengo que programar?

R: me imagino que es lo mismo que la actividad anterior sobre la pregunta del opengl nuevo  el antiguo y es en si que es mas moldeable para el programdador de que se muestra en la imagen, no e tan fijo ni tan lineal el programdor puede darle forma a lo que quiera mostrar segun lo que se necesite sin seguir ciertas cosas ya establecidas

Si fueras a describir el proceso de rasterización ¿Qué dirías?

R: Diria que es un proceso fundamental en la imagen y que tiene mucho que ver con el frame buffer y con el viewport, ya que en si es el que maneja el tema de como se muestra cada cosa en la pantalla, osea primero se diseña que se va ver y despues viene el rasterization para segun lo que se pida darle vida a eso y con los pixeles de la pantalla segun su resolucion darle la forma, ojo no el color eso ya es trabajo del siguiente

¿Qué son los fragmentos? ¿Es lo mismo un fragmento que un pixel? ¿Por qué?

R: los fragmentos y los pixeles no son lo mismo pero uno contiene al otro, los fragments son grupos de pixeles de un triangulo que lo forman

Explica qué problema resuelve el Z-buffer y ¿Qué es el depth test?

R: El z buffer o el deph buffer resuleve el problema principal de que pues que por ejemplo, el vertex shaping ya tiene lo que hay que mostra listo con vetcies triangulos y todo, pero como todo videojuego 3d hay ciertos angulos en donde hay partes que pues se tapan entre si entonces no se van a ver y estra renderizando todo eso a la vez pues es imposible y si se pudiera no seria muy bueno para la memoria, eso o resuleve el z buffer que mediante el sistemas de cordenandas que se explica que utiliza el resterization que acomoda os pixeles en ciertos lugar, saca ademas de los valores X y Y un valor Z, que no es en si porque sea un ambiente  un juego 3D, o pues si porque es para resolver un problema en un juego 3d, pero no es en si enfocado en eso, si no que saca el valor en z de los veertices y de los pixeles lo cual cada pixel se le da un valor de z diferente si esta mas cerca o mas lejos, si esta mas cerca eso indica desde la vista de la camra al rasterization que pixel mostrar y cual no dependiendo la perpectiva de ese frame en especifico y esto para resolver ese problema.

¿Por qué se presenta el problema de la aliasing? ¿Qué es el anti-aliasing?

R: el aliasing se da que en si auqnue al principio se definan las escenas de los video juegos en triangulos y vertices y todo muy lindo la realidad de lo que se le va mostrar al usuario es otra, y es que por el momento tdoas las antallas funcionan de acuerdo a pixeles osea cuadrados y esto mas que todo se ve en pantallas con poca resolcion o colocandole una baja resolucion , lo que es es que se notan los famosos dientes de cierra que hace ver la imagen fuera de como una simulacion de la vida real, algo que se ve feo, entonces el anti aliasing o el SSAA lo soluciona, consumiendo mas memoria y mas recursos de la gpu pero haciendo que la imagen se vea mas pulcra.

¿Qué relación hay entre la iluminación y el fragment shader? Siempre es necesario tener en cuenta la iluminación en un fragment shader? o puedo hacer un fragment shader sin iluminación? Explica que implicaciones tiene esto.

R: la relacion entre iluminacion y el fragment shading que es el ultimo paso en el proceso de mostrar una imagen es basicamente que el fragment shading calcula los distintos tipos de iluminacion que hay en una escena de un videojuego por ejemplo para mostrarlo por asi decirlo mucho mas realista, y siempre es primordial porque si no se tuviera en cuenta el fragment cololearia los pixeles pero tdoo se veria como una escena mal hecha como para nios sin un realimso notorio, por eso es que se toma en cuenta la iluminacion, y si se podria hacer pero pues en resumen se veria horrible y con muy poco detalle la escena.

¿Qué implica para la GPU que una aplicación tenga múltiples fuentes de iluminación?

R: mucho mas consumo en memoria y recursos lo cual se veria en mucha mejor calidad pero mas sacrificio de recursos, pero ues para eso es que estan diseñadas y en especia las tarjatas graficas dedicadas para que ellas solas se encargen de eso y no tener que sacrificar otros aspectos importantes del pc como la ram o la misma cpu, esto por ejemplo es un problema muy frecuente en las graficas integradas en la cpu que si que se encargan de las tareas graficas pero le roban una gran parte de la memria a la cpu lo cual se traduce en mas demanda de recuross para la gpu y menos rendimiento para porcesos simples del computador.


🧐✍️ Reporta en tu bitácora

Es momento de hacer digestión cognitiva. Debemos parar de nuevo en este punto y consolidar. Para ello te pediré que hagas lo siguiente:

Escribe un resumen en tus propias palabras de lo que se necesita para dibujar un triángulo en OpenGL.

R: Siguiendo lo aprendido y deciendolo en mis propias palabras mas o menos resumida mente voy a seguir un poquito la logica del video y aplicarla aen esto, y pues por lo que entiendo es que primero lo primero definimos los vertices en donde se va esamblar el triangulo que queremos dibujar, despues mediante el rasterization utilizando los pixeles y los sahders y toda la informacion que e damos paa que se dibuje correctamente lo que queremos y la resolucion de la pantalla llenamos ese triangulo con los pixeles necesarios, despues con el fragment shading lo coloreamos de lo que necesitemos y ya. 

y pues los vertices y el tamaño del trianuglo se encarga el rasterization segun la resolucon que pongamos en la ventana, ya sea en pantalla completa o en una pequeña ventanita o como sea pero a ciencia cierta si nos fijamos entre la distancia de los vertices del triangulo a los bordes de la ventana es exactamente la misma si no que a medida que la "resolucion" de la ventana aumenta, el triangulo tambien lo hace.


Escribe un resumen en tus propias palabras de lo que necesitas para poder usar un shader en OpenGL.

R: 
pues con lo explicado me queda claro que es si o si obligatorio usar shaders en el opengl actual, y aqui se utlizan para lo vertices y para colorear y darle forma al triangulo que queremos

y lo que se necesita primero es crear un obejto que tendra nuestros shaders y que se hace en una funcion paa este y se le da un id unico para cada llamada de opengl


## Actividad 05

🧐🧪✍️ Reporta en tu bitácora

Modifica el código del triángulo para que sea interactivo.
Incluye una captura de pantalla del triángulo interactivo funcionando en tu máquina.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4500d1ab-f074-434d-a705-599c77f08665" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dbb43e03-0cca-4981-b31c-0011b7963a7c" />


Explica el proceso de normalización de las coordenadas del mouse y cómo se relaciona con el sistema de coordenadas de OpenGL.

R:

Estos valores en píxeles no son muy útiles para OpenGL directamente, ya que dependen del tamaño de la ventana. Si usáramos los píxeles directamente, nuestro código se rompería al cambiar el tamaño de la ventana. Al normalizar, creamos un sistema de coordenadas relativo e independiente de la resolución. Un valor de x = 0.5 siempre representará el centro horizontal de la ventana, sin importar si esta mide 400 o 1920 píxeles de ancho.

¿Cómo se hace? La fórmula es muy simple:
coordenada_normalizada_x = posicion_x_en_pixeles / ancho_total_de_la_ventana

coordenada_normalizada_y = posicion_y_en_pixeles / alto_total_de_la_ventana

Explica el proceso de normalización a coordenadas de dispositivo (NDC) y cómo se relaciona con el sistema de coordenadas de OpenGL.

R:

Las Coordenadas de Dispositivo Normalizadas (NDC) son el sistema de coordenadas fundamental en el que OpenGL opera después de que tu Vertex Shader ha hecho su trabajo. Es la "meta" para todas las posiciones de los vértices.

¿Qué es el sistema NDC? Es un pequeño cubo donde los ejes X, Y y Z van todos desde -1.0 hasta 1.0. El punto (0, 0) es el centro exacto de la pantalla.

(-1, 0) es el centro del borde izquierdo.
(1, 0) es el centro del borde derecho.
(0, -1) es el centro del borde inferior.
(0, 1) es el centro del borde superior.

¿Cómo se relaciona con OpenGL? Cualquier vértice que el Vertex Shader envíe a la variable gl_Position debe estar en este espacio de coordenadas NDC. Si un vértice cae fuera del rango [-1, 1] en cualquier eje, será recortado y no se dibujará en la pantalla.

## Actividad 06
🧐🧪✍️ Reporta en tu bitácora

Describe brevemente los cambios que realizaste en el código C++ (dónde obtienes el tiempo, cómo y dónde actualizas el uniform).

R: describiendo brevemente lo que hice fue que parti en si del codigo normal del  inicio para poder hcaerlo ya que en este computador no tenia lo de la actividad 5, primero como no parti de la actividad 5 tuve que modificar el codigo primero corrigiendo unas errores de las ctiviades pasadas y despues poniendo entre el paso 14 en el while entre el paso 14 y el 15 esta parte de codigo que es el bucle que hace que se pueda obtener el tiempo para despues pasarlo al shader

<img width="707" height="326" alt="image" src="https://github.com/user-attachments/assets/988f7b88-9a47-44dc-9cd0-5f35367d5511" />

y por ultimo hice uns pequeños cambios utilizando la funcion sen y sumandole 1 y diviendola en 2 para poder que tueviera un rango de 0 a 1 y que oscilara en ese rango que despues se declara como una variable para utlizarla en nuestro rgb para remplzarla por el valor del rojo y asi hacer que sea como un pulso, que el trigangulo cambie de colores constanetmente

<img width="640" height="413" alt="image" src="https://github.com/user-attachments/assets/66237596-7489-4124-bb59-03e6affbff2e" />


Pega el código modificado de tu fragment shader.

```

const char* fragmentShaderSrc = R"glsl(
    #version 460 core
    uniform float u_tiempo;
    out vec4 FragColor;
    void main() {
        float mi_valor = (sin(u_tiempo) + 1.0) / 2.0;
        FragColor = vec4(mi_valor, 0.5, 0.2, 1.0);
    }
)glsl";
```

Explica cómo usaste la función de tiempo (sin, cos, u otra) para lograr el efecto de cambio de color cíclico. ¿Qué rango de valores produce tu cálculo y cómo afecta eso al color final?

R: ya lo explique en el primer punto pero igualmente vuelvo a explicarlo que en si lo que se hace con el sen es que su rango osea e la funcion sen se sabe que es de 1 a -1 entonces aqui lo que hacemos es sumar 1 a la funcion lo cual hace que su rango pase a ser de 2 a 0 y ahi dividimos entre 2 para que quede un rango de 1 a 0, esto sirve para como representar el valor de rojo que es lo que queremos en esta actividad que es hacer un palpito del rojo que se vea fuerte y luego baje su intensidad como titilando, entonces al estar en ese rango hacemos que oscile entre 0 y 1 asi bajando y subiendo su intensidad asi haciendo el efecto visual que eueremos conseguir

Incluye una captura de pantalla o UN ENLACE a un video mostrando el resultado del triángulo con color cambiante.

<img width="1919" height="1068" alt="image" src="https://github.com/user-attachments/assets/67f40c71-c3c3-4ecf-8a4f-5177273f1375" />

Asi esta primero cuando esta opaco

<img width="1916" height="1077" alt="image" src="https://github.com/user-attachments/assets/12dba2ff-f7d3-47ec-a27a-583d83f0f93b" />

y asi esta despues y ya asi se repite


Reflexión: ¿Qué otros efectos visuales simples podrías lograr usando el tiempo como uniform? Piensa en la posición, el tamaño o la rotación (aunque no hemos visto rotaciones formalmente, ¡intuitivamente podrías intentarlo!). Anota al menos una idea.

R: primero pues que los vertices se puedan mover y asi hacer un efecto que sea como que el triangulo se hace mas grande y mas chicos y asi repetidamente y asi haciendo como un efecto de palpito

y pues pienso que se podria hacer rotando el triangulo sobre su mismo eje

## AUTO EVALUACION UNIDAD

considero que mi nota puede ser de 5 y que todas las actividades fueron resueltas correctamente y sin ningun problema
