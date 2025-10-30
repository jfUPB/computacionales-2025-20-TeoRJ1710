# Bitácora de aprendizaje de la unidad 8

## Actividad 01

🧐🧪✍️ Reporta en tu bitácora

Ejecuta el programa y haz clic en la ventana. Observa lo que sucede. ¿Qué es lo que ves? ¿Qué es lo que esperabas ver? ¿Por qué crees que sucede esto?

R: lo que veo es un circulo negro que va de un lado a otro que que al momento de darle click a la pantalla el circulo cambia de tamaño y no se si es porque mi computador es muy lento pero se detiene y se lagea y despues vuelve a empezar con el nuevo tamaño y a la velocidad de la luz y despues vuelve a su velocidad normal. y pues creo que sucede esto de que se traba porque esta ocupando mucha memoria o los procesos de cambio de tamaño no dejan que los procesos de mostrar la imagen en cda frame funcionen y es por eso que se ve trabado.

🧐🧪✍️ Reporta en tu bitácora

Ejecuta el programa y haz clic en la ventana. Observa lo que sucede. ¿Qué es lo que ves? ¿Qué es lo que esperabas ver? ¿Por qué crees que sucede esto?

R: Ahora lo que veo es que la aplicacion no se detiene bruscamente y para su proceso de dibujado si no que veo y interpreto que hace el proceso aparte para poder segir mostrando imagen mientras que el proceso para designar un nuevo tamaño al circulo sigue su funcionamiento


Observa que el programa ahora no se congela, pero el círculo no cambia de tamaño inmediatamente. ¿Por qué crees que sucede esto? ¿Qué es lo que está pasando?

R: interpreto que es lo mismo que lo anterior si no que ahora separamos el proceso de dibujado del circulo para que no se interfiera por el cambio de tamaño pero el proceso sigue siendo igual de lento

🧐🧪✍️ Reporta en tu bitácora

En tus propias palabras, explica la diferencia entre concurrencia y paralelismo. ¿Por qué es importante entender esta diferencia al trabajar con hilos?

R: que concurrencia es un metodo en el cual utilizando un solo nucleo las tareas se ejecutan de forma que se intercalan como en el primer ejemplo que se van prestando el turno para poder hacer sus procesos, lo cual lo vuelve tosco en ciertos casos, y el paralelismo es realmente la forma que las tareas se ejecuten varias a la vez sin incomvenientes, osea una en realidad hace que el programa pueda ser mejor y que se vea mejor y sea mas rapido porque puede hacer varias cosas a la vez en cambio que el otro seria un poco mas tosco y menos util a mi parecer.

## Actividad 02

🧐🧪✍️ Reporta en tu bitácora

1. Analiza de nuevo el código de la actividad anterior. ¿En qué partes del código se está protegiendo el acceso a la variable circleSize?

El acceso a la variable compartida circleSize se protege en las siguientes secciones del código dentro de ofApp.cpp:


Función ofApp::draw() (Hilo Principal):


````
lock();
ofDrawCircle(x, ofGetHeight() / 2, circleSize); // Leer circleSize
unlock();
````

Función ofApp::heavyComputation() (Hilo Secundario):



````
lock();
ofSeedRandom();
circleSize = ofRandom(20, 70); // Escribir circleSize
unlock();
````

La protección se realiza usando los métodos lock() y unlock() que hereda la clase ofApp de ofThread, los cuales actúan como un mutex (mecanismo de exclusión mutua) para garantizar que solo un hilo a la vez pueda leer o escribir la variable circleSize.

2. Según lo que te he venido comentando, los hilos te permiten ejecutar tareas en paralelo; sin embargo, piensa qué ocurre con el paralelismo cuando se sincroniza el acceso a un recurso compartido. ¿Qué ocurre con el rendimiento del programa? ¿Es posible que el rendimiento se vea afectado por el uso de mutex? ¿Por qué?

R: El rendimiento del programa se ve afectado y el beneficio del paralelismo se limita por el uso de un mutex.
La sincronización con lock() y unlock() asegura que solo un hilo a la vez pueda acceder a la sección de código protegida. Cuando un hilo adquiere el lock, cualquier otro hilo que intente acceder debe esperar (bloquearse) hasta que el primer hilo libere el lock. Si muchos hilos tienen que esperar continuamente por el mismo recurso, pasan tiempo ociosos en lugar de ejecutando trabajo en paralelo, lo que reduce drásticamente las ganancias de rendimiento.


🧐🧪✍️ Reporta en tu bitácora

Ejecuta el código y observa el resultado. ¿Qué ocurre si cambias el valor de la variable useLock? ¿Por qué crees que ocurre esto?

R: 

El valor de Contador será igual al Esperado.Y pues pienso que esto ocurre porque el acceso a la variable compartida counter está protegido por el lock, garantizando que cada incremento se complete atómicamente y sin interferencia de otros hilos.

El valor de Contador será menor que el Esperado, pues por ejemplo, podría ser 3987123. Esto ocurre porque no hay sincronización, lo que genera una Condición de Carrera y se pierden actualizaciones.

🧐🧪✍️ Reporta en tu bitácora

Explica en tus propias palabras ¿Cómo puede presentarse la condición de carrera en este caso? ¿Qué es lo que está pasando? Te pido que propongas un ejemplo.

R: La condición de carrera se presenta porque la operación ++(*counter) no es atómica, ya que el procesador la descompone en tres pasos que son leer incremntar y poner, osea que cuando uselock es falso esto puede hacer que dos hilos de entorpescan y se intercepten

<img width="766" height="258" alt="image" src="https://github.com/user-attachments/assets/15176a74-8efa-4c1e-9a23-64ed278a5f6f" />

algo asi, ahi se ve que cada hilo esta ejecutando un incremento pero el resultado es 101, cuando el resultado que se espera es 102, por lo cual se esta perdiendo un incremnteo o actualizacion etc.


## Actividad 03

🧐🧪✍️ Reporta en tu bitácora

Ejecuta el código y observa el resultado.

R:

Pues ejecutandolo y viendolo veo que se muestra el fractal, veo tambien que se ejecuta el tiempo de calculo y si en el paralelo el tiempo de carga es mucho menor

<img width="1919" height="1080" alt="image" src="https://github.com/user-attachments/assets/ef83f4d1-1b20-4459-a7d2-ac05e4701f4c" />

Te dejo una idea para comenzar a experimentar: ¿Qué ocurre si cambias el número de hilos? ¿Por qué crees que ocurre esto?

R: pues primero a ver mi hipotesis es que dependiendo de la GPU si el nuemro de hilos es mayor a los de la gpu evidentemente se espera que el rendimiento caiga, y si es menor pues se espera que mejore o que se mantenga minimanemte

y pues evidentemente el tiempo de calculo como se espera en la paralela es mucho menor que en la secuencial, y esto es por la hipotesis, y pues digamos que si el numero de nucleos que se pone ahi es mayor puede que no se vea como el bajo de rendimiento pero esta claro que mas alla de lo que nos ofrece la gpu no va dar, entonces evidentemente el resulta es que se mantiene o se merma porque estamos sobrecargando el nuemro de hilos de la cpu, en cambio si el numero es menor mejora el rendimento ya que no estamos sobrecargando nada, igual tampoco es reconmendable por lo que yo pienso utilizarlos todos en su totalidad porque recordemos que la cpu no se ocupa solo de una cosa.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/99e36aef-38ca-4a01-a5ef-f27e33098185" />

con solo mirar el numero de fps se da cuenta de la sobre carga que se le da en el proceso.

## Actividad 04
🧐🧪✍️ Reporta en tu bitácora

Observa ambos códigos y responde a las siguientes preguntas:

¿Cuál es la estructura de datos principal que contiene la información de todos los boids y que es accedida por múltiples hilos (el hilo principal para dibujar, el hilo trabajador para actualizar)?

R: El vector std::vector<Boid> boids dentro de la clase Flock.

Observa la función Flock::threadedFunction() donde el hilo trabajador calcula el movimiento. ¿Qué operaciones realizan sobre el vector de boids compartido?

R: Lectura y Escritura o Modificación.

Observa la función ofApp::draw(). ¿Qué operación realiza sobre el vector compartido?

R:  Lectura ya que recorre contsnatementye el vector para llamar a draw

Observa Flock::addBoid() y ofApp::mouseDragged(). ¿Qué operación realizan?

R: Escribir o modificar si ese es su caso, añadiendo un elemento nuevo al vector

Describe un escenario específico y concreto donde la falta de sincronización podría causar un problema. Por ejemplo:

R: un planteo posible podria ser redimensionamiento de vector durante Recorrido. El hilo trabajador comienza un bucle para actualizar los boids, justo despues el hilo prncipal añade un nuveo void y el vector se redmiemnsiona y manda los boids a otra parte, pero el principal sigue creando en un punto donde ya no estan ya no existen osea es invalido, y pues lo mas probable es que ocurra un crash.

Localiza todas las llamadas a lock() y unlock() dentro de la clase Flock (o donde se acceda al vector compartido).

R:

Hilo trabajador
<img width="258" height="160" alt="image" src="https://github.com/user-attachments/assets/2c474e9b-3909-42b2-825b-d46813a1e3c8" />

Hilo principal modifica
<img width="271" height="92" alt="image" src="https://github.com/user-attachments/assets/960169b2-a8b3-4458-aaaf-fea5404aea2c" />

Hilo principal lee
<img width="293" height="139" alt="image" src="https://github.com/user-attachments/assets/07019921-234c-4b2f-8955-de10281fd5d3" />


Justificación: para uno de los escenarios problemáticos que describiste arriba, explica cómo las llamadas a lock()/unlock() en las secciones de código relevantes evitan que ocurra ese problema específico.

R:
La sincronizacion ayuda o evita mas que todo el problema de redimensionamiento de forma que si el hilo trabajdor ya adquirio a Flock::threadedFunction() el hilo principal que llama a flock addboid  no podra obtener el lock y quedara bloqueado hatsa que el hilo trabajdor termine su bucle y llame a unlock

Aunque los locks aseguran la correctitud, ¿Puedes intuir por qué tener muchos hilos esperando para adquirir un lock sobre el mismo vector (alta contención) podría limitar el beneficio de rendimiento del paralelismo en este caso? Justifica tu respuesta.

R: se limita el rendimeinto porque una cosa y otra no van de la mano en sentido practico y eficaz, la alta cohesion limita el paralelismo porque como se dice son muchos hilos esperando el mismo lock
y mi justificacion es que el tiempo que pasan bloqueados por lo ya antes dicho esperando un solo lock reduce o anula el beneficio de haber lanzado multiles hilos por eso digo que no van de la mano en forma practica y eficaz



🧐✍️ Reporta en tu bitácora

Este es un ejercicio mental y de reflexión, no tienes que implementar nada, solo pensar:

Piensa en la pregunta que te acabo de hacer. ¿Qué pasaría si tuviéramos varios hilos que calculan el movimiento de los boids? ¿Cómo podrías implementar esto? ¿Qué problemas crees que podrían surgir? ¿Cómo podrías solucionarlos?

R. yo lo que implementaria seria similar al Mandelbrot: Dividir el vector boids en subconjuntos de boids. Cada hilo ejecuta el bucle de simulación (b.run()) solo para su subconjunto asignado.
Ahora el problema y un gran problema que podria suceder es que los boids aqui necesitan saber como estan los otros boids osea pues sus vecinos, pero podria pasar que otro hilo este modificacndo los datos de ese boid a la vez que el otro hilo trata de leer la posicion por asi decirlo del vecino lo cual podria dar errores o ver quien primero lee o modifica
y para solucionarlo se podria poner un lock en cada boid pero no lo veo tan viable entonces propongo que antes de inicair el hilo principál cree una copia de una sola lectura para todos los boid, los trabajadores trabajn sobre esa copia y ya los nuevos resultados son usados por el hilo principal para aplicar todos los resultados a los boid reales.

🧐🧪✍️ Reporta en tu bitácora

Analiza el código del Flocking sin hilos y el Flocking con hilos.
¿Qué diferencias encuentras? ¿Por qué crees que es importante la sincronización en el segundo caso?

R: 

Diferencias: En la versión con hilos, el cálculo del movimiento (Flock::threadedFunction()) se ejecuta en un hilo separado del dibujo (ofApp::draw()). Importancia de la Sincronización: Es crucial porque el vector boids es compartido. Tanto el hilo trabajador (modifica) como el hilo principal (lee para dibujar y modifica al añadir) acceden a él. La sincronización (lock/unlock) evita que un hilo intente, por ejemplo, dibujar el vector (leyendo) justo cuando otro hilo intenta añadirle un elemento (modificando y posiblemente redimensionando), lo que causaría un error o crash.

¿Por qué al añadir un nuevo boid la simulación se ralentiza? ¿Qué ocurre si añades muchos boids?

R:

La simulación se ralentiza porque el cálculo del flocking es $O(n^2)$ (cada boid interactúa con casi todos los demás). Al añadir un boid (incrementar $n$), el tiempo de cálculo por frame aumenta cuadráticamente. Si añades muchos boids, el tiempo de cálculo se vuelve tan largo que el FPS baja drásticamente o la aplicación se congela (en la versión sin hilos).


Notaste que la versión con hilos tiene un sleep(5) en el hilo trabajador. ¿Por qué crees que se ha añadido? ¿Qué pasaría si lo eliminamos?

R:

El sleep(5) (milisegundos) se añade para limitar la velocidad de actualización del flocking (ej. a 200 veces por segundo, $1000/5=200$). Si lo eliminamos, el hilo trabajador intentaría recalcular el flocking tan rápido como el CPU lo permita (posiblemente miles de veces por segundo). Esto consumiría el 100% de un núcleo del CPU innecesariamente, calentando el procesador y potencialmente robando tiempo de CPU al hilo principal de dibujo, lo que podría hacer que el framerate de la UI bajara (peor eficiencia energética y peor responsividad en algunos casos).


Compara el rendimiento de ambos enfoques. ¿Cuál crees que es más eficiente? ¿Por qué?

R:

Ambos son igualmente eficientes en el cálculo puro del flocking (ambos lo hacen de forma secuencial). Sin embargo, el enfoque con hilos es percibido como más eficiente y responsivo porque: 1. Mantiene el FPS del dibujo alto (UI fluida). 2. Permite la interacción (añadir boids) incluso durante el cálculo pesado. El hilo trabajador puede calcular más lento si es necesario (gracias al sleep), lo que puede hacer que la eficiencia energética sea mejor, pues no intenta calcular el flocking más rápido de lo necesario para que el ojo lo perciba.


🧐✍️ Reporta en tu bitácora

¿Qué ocurre si mientras el hilo trabajador está calculando el movimiento de los boids, el hilo principal intenta añadir un nuevo boid? ¿Se congelará la aplicación? ¿Por qué?

R: no no se congelaria, y por lo que entiendo es porque el hilo principal que llama a addboid y addboid intenta conseguir el lock y como el hilo trabajdor tiene el loc el hilo principal se bloqueara hasta que el lock no lo libere el trabajador, y mas o menos entiendo que se intenta comparar con la actividad 1 porque vemos que la imagen se congela por un momento hasta que vuelve y inicia, esto aqui no pasa, si se veria una micropausa pero no mas de un segundo si es mucho, por lo cual no se deberia de congelar
