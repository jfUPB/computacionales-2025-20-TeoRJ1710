# Bitácora de aprendizaje de la unidad 6
## ACTVIDAD 01

¿Cómo puedes interactuar con la aplicación? Menciona específicamente las teclas y qué efecto parecen tener sobre las partículas.

R: A las atrae como un iman al metal, R hace lo contrario las repele como el polo opuesto de un iman contra otro iman, s las congela, y n las vuelve a mover

¿Observas los diferentes tipos de “partículas”? ¿Se comportan todas igual inicialmente?

R. pues en si diferente en base a su funcinamiento no son, son de diferente color pero alcanzo a ver solo con interactuar con el programa sin ver el codigo que las particulas se atraen de la misma manera todas a la misma velocidad, se repelen se detienen y se vuelven a iniciar de la misma manera, eso si cuando se pasa con s y se vuelve a inciar con n como cuando ejecutas la aplicacion por primera vez se ve que las particulas si tiene un movimiento aleatorio y desordenado y acada cual va por donde quiera, a no ser que uno las atraiga

Toma algunas capturas de pantalla de la aplicación en diferentes momentos (estado inicial, después de presionar ‘a’, ‘r’, ‘s’, ‘n’) y añádelas a tu bitácora.

<img width="1812" height="1079" alt="image" src="https://github.com/user-attachments/assets/66c86c54-c4ea-462c-8ffb-572b58e3fd30" />
aqui es al principio del codigo sin ejecutar ningunsa accion

<img width="1706" height="1019" alt="image" src="https://github.com/user-attachments/assets/98ecf4a6-e064-4e89-bb8d-fdaf59d0e2b1" />
Aqui Se estan atrayendo on el mouse al presionar a

<img width="1584" height="1052" alt="image" src="https://github.com/user-attachments/assets/be65dc29-ad1c-4645-91ec-52e3946b456d" />
y aqui presione r para que se repelieran

<img width="994" height="779" alt="image" src="https://github.com/user-attachments/assets/5cd13720-5619-462c-bdc0-23f17811cdab" />
Aqui presione N para que se vlvieran a dispersar

y pues al preiosnar s se paran o se congelan pero pues tpmar captura de eso pues no tiene sentido


¿Qué crees que está pasando “detrás de cámaras” cuando presionas las teclas? Formula una hipótesis inicial sobre cómo la aplicación cambia el comportamiento de las partículas.

Yo me imagino que al momento de presioanr un tecla y por el tema que estamos viendo en esta unidad al momento de presionar por ejemplo A que es cuando todas se atraen al mouse, al momento hay algo organizando todas las particulas que al momento de el de cambiar de estado con la tecla A por ejemplo notifica a todas las particulas que el organiza y todas cambian su estado y asi con todas las teclas

### AUTOEVALUACION DE LA ACTiVIDAD

considero que con las capturas y todo lo documentado perfectamente la nota puede ser 5

## Actividad 02

Explica con tus propias palabras el propósito del patrón Observer. ¿Qué problema resuelve?

R: para mi el problema principal que resuelve usar el metodo observer en el caso de estudio que tenemos por lo que entiendo hasta ahora es que no se necesita hacer como un controlador por cada particula que le diga a esa particula que hacer segun lo que nosotros queramos segun las teclas que presionemos, si n que mas facil organizado y mas eficaz hace que como se dijo en el ejemplo principal haya uno solo que sea el que se le indique las acciones, el que cambie de estado y el que a la par indique o pues notifique a todas las particulas que tienen que hacer para que ellas se actualizen. Osea mejora la organizacion, simplifica las cosas, y lo vuelve mas eficaz.


Dibuja un diagrama que muestre la relación entre Subject, Observer, ofApp y Particle en el caso de estudio, indicando quién es el Sujeto y quiénes los Observadores.

R:
<img width="361" height="690" alt="image" src="https://github.com/user-attachments/assets/1728274e-3f5e-4b1b-837a-74052d863fbb" />


Construye un diagrama de secuencia que muestre cómo funciona el patrón Observer al presionar una tecla.

R:

<img width="1229" height="607" alt="image" src="https://github.com/user-attachments/assets/98529cf0-3242-4435-b437-0d15f30b7915" />



¿Qué ventajas crees que ofrece usar el patrón Observer en esta aplicación en comparación con, por ejemplo, que ofApp::update recorriera todas las partículas y les dijera directamente que cambien su comportamiento basado en una variable global? Piensa en términos de acoplamiento y extensibilidad.

R: primero seria que por ejemplo a comparacion de una variable local las particulas estan limitadas a esa variable local y si se quiere hace una particula diferente hay que modificar muchas cosas, y con esto no es necesario ya que se pueden tener multiples observadores todos con funciones diferentes asi dadndo las diversidad y capacidad al codigo, tambien que por ejemplo ofApp solo necesita notificar el evento, osea la accion que hacemos para poder hacer que las particulas cambien, esa es su unica responsabilidad y las particulas ya se encargan de acatar la orden.

### Autoevaluacion de la actividad

todas las actividades desarrolladas, considero que fue un buen desarrollo creo que los mapas estan correctos y el analisis de mis respuestas fue correcto, pero por la duda de los mapas yo considero que un 4 para esta podria estar bien

## Actividad 03

Explica con tus propias palabras el propósito del patrón Factory Method (o Simple Factory, en este caso). ¿Qué problema principal aborda en la creación de objetos?

R: pues basandome en el enunciado de la actividad como lo hice en la actividad pasada puedo decir que basandome en el caso de estudio es lo que se utiliza para separar la creacion de todas las particulas aparte como una particlefactory en vez de tener un new particle.

y pues por lo que entiendo soluciona principalmente que facilita añadir nuevos tipos de objetos sin tener que modificar en muchos sitios del código.


¿Qué ventajas aporta el uso de ParticleFactory en ofApp::setup en comparación con instanciar y configurar las partículas directamente allí? Piensa en términos de organización del código (SRP - Single Responsibility Principle), legibilidad y facilidad para añadir nuevos tipos de partículas en el futuro.

R: 

organizacion: 

ofapp lo unico que tiene que hacer es delegar responsabilidades como darle la responsabilidad de la creacion de particulas a factoryparticle


simplicidad:

En lugar de tener 20 líneas repitiendo configuraciones como de crearla de darle estos atributos y estos, ofApp solo llama a ParticleFactory


Modificacion y manipulacion facil:

Si en el futuro queremos agregar más tipos de partículas solo tenemos que modificas factory y miles de lineas de codigo de ofapp


Imagina que quieres añadir un nuevo tipo de partícula llamada "black_hole" que tiene tamaño grande, color negro y velocidad muy lenta. Describe los pasos que necesitarías seguir para implementar esto utilizando la ParticleFactory existente. ¿Tendrías que modificar ofApp::setup? ¿Por qué sí o por qué no?

R: respondiendo primero a la pregunta segun la logica de todo lo anterior visto NO porque como se explico la unico que necesita hace ofapp es delegar responsabilidades asi que todo el proceso de crear una partucla tiene que ser de particlefactory por lo cual yo considero que no se necesita modificar

yo lo añadiria primero en particle factory añadir un nuevo else if y despues tipo black_hole y despues todos sus atributos, tamaño, color etc ( pues yo segui mas o menos la guia que ya estaba en el resto ya creadas en la factory
podria quedar algo asi:
<img width="620" height="396" alt="image" src="https://github.com/user-attachments/assets/044beb51-13f8-496b-9ac9-938f539cab98" />

y me acabo de dar cuenta que lo unico que habria que cambiar seria la llamada a la particula en ofapp, pero de resto no veo nada mas que cambiar ahi.



El método createParticle en el ejemplo es estático. ¿Qué implicaciones (ventajas/desventajas) tiene esto comparado con tener una instancia de ParticleFactory y un método de instancia createParticle()?.

R:
por lo que puedo ver de ventajas es que este codigo tal cual como esta le combiene que se estatica porque no se requiere instnaciar la fabrcia por lo cual al repasar es menos memoria usada ( y pues tambien ya que es un proyecto simple pues le queda muy bien), pero pues en parte en desventajas por lo que comente si fuera un proyecto grande por ejemplo seria menos flexible, por ejemplo no se podria heredar para tener distintos tipos de fabricas de muchos distintos tipos de particulas.

### Autoevaluacion actividad 03

considero que las respuestas estuvieron bien completas y bien argumentados, fuera de algun fallo en alguna respuesta yo me pondria 5.


## Actividad 04

Explica con tus propias palabras el propósito del patrón State. ¿Cuándo es útil aplicarlo?

R: Por lo que entendi tambnien como antes de los enunciados de las actividades el patrón State sirve para que un objeto cambie su comportamiento según el estado en el que esté, sin necesidad de usar if/else gigantes.
por lo cual es util caundo se quiere que el codigo sea facil de mantener modificar y entender



Dibuja un diagrama de estados simple para la clase Particle. Muestra los diferentes estados (Normal, Attract, Repel, Stop) como nodos y las transiciones entre ellos como flechas etiquetadas con el evento que las causa (p. ej., la tecla presionada: ‘n’, ‘a’, ‘r’, ‘s’).

R: 
<img width="722" height="452" alt="image" src="https://github.com/user-attachments/assets/75906d51-a969-4319-8998-74622a999ea4" />


Describe las ventajas de usar el patrón State en Particle en lugar de tener un miembro std::string estadoActual y usar un gran if/else if/else o switch dentro de Particle::update() para cambiar el comportamiento. Piensa en cohesión, extensibilidad (añadir nuevos estados) y el Principio Abierto/Cerrado (Open/Closed Principle).

R:

Cohesión: Cada estado tiene su propia clase con su lógica. No se mezclan todos los comportamientos en Particle.

Extensibilidad: Si quiero un nuevo estado (BounceState por ejemplo), solo creo una nueva clase, sin tocar el código viejo.

Principio Abierto cerrado: El código de Particle está “cerrado” a modificaciones pero “abierto” a extensiones, porque delega todo en los estados.


¿Qué responsabilidad tienen los métodos onEnter y onExit en el patrón State? Proporciona un ejemplo de por qué podrían ser útiles (incluso si no se usan mucho en todos los estados de este caso de estudio). Por ejemplo, ¿Qué podrías hacer en onEnter para AttractState o en onExit para StopState?>

R: En si las responsabilidades son que onEnter se ejecuta cuando un objeto entra a un estado. Sirve para inicializar algo o lanzar una animación y onExit se ejecuta cuando sale del estado. Sirve para limpiar o restaurar cosas.
y pues el ejemplo que puedo dar es que en AttractState::onEnter se podría hacer que la partícula cambie de color a azul para indicar que está siendo atraída y en StopState::onExit se podria resetear la velocidad de la partícula a 0 antes de moverse de nuevo.

### Autoevaluacion de la act 04
Todas las actividades completas, el diagrama considero que esta bien, yo considero qeu estuvo bien para un 5

## Autoevaluacion de la unidad

Me voy a colocar un 4 por la obvia razon que no pude hacer la act 5 a tiempo por temas de tiempo por otros compromisos, considero que puede ser un 4 a mi parecer, porque se que algunos de mis analisis y respuestas estan mal y probablemente este mal, y aunque en alguno lugares admito que si me toco repasar de antes y investigar me quedo con que hice el esfuerzo en la amyoria de la unidad de hacer todo por mi cuenta
