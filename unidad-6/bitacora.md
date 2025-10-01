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
