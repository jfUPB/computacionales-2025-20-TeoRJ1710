# Unidad 3


## 🛠 Fase: Apply

### ACTIVIDAD INTEGRADORA

1: IDENTIFICAR LOS ERRORES

ERROR #1

<img width="652" height="85" alt="image" src="https://github.com/user-attachments/assets/6227c88a-73dc-4460-a6d1-82c837fdf18e" />

En el constructor se hace new int pero nunca se libera. Esto se da ya que el arreglo vive en el heap. El objeto Personaje vive en el stack de simular Encuentro. Al salir de la función, se destruye el objeto del stack, pero el arreglo del heap queda huérfano. y esto hace que como consecuencia la ram crece con cada personaje creado, segun el nivel de esto esto puede llevar a acumulacion de memoria usada y a mayor demanda y a menos cantidad de ram disponible por parte del pc puede llevar a posibles craseos




ERROR # 2

<img width="565" height="332" alt="image" src="https://github.com/user-attachments/assets/af9ff3a6-7e0a-448d-aa9b-f12ae7520818" />

Personaje tiene un puntero propietario int* pero no define constructor de copia, entonces la copia por defecto duplica el puntero, no los datos. Esto se da ya que despues de Personaje copiaHeroe = heroe;, ambos objetos quedan apuntando al mismo arreglo del heap. Esto rompe con la idea de que modificar uno afecta al otro. Si en el futuro alguien agrega un destructor que haga delete[] ocurrirá que haya un craseo. Y pues esto puede traer varios tipo de consecuencias pero lo mas evidente fuera de lo ya mencionado son craseos muy frecuentes a causa de esto.
