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
