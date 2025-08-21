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


2: SOLUCION Y SU JUSTIFICACION


```
include <iostream>
#include <string>
#include <array>

class Personaje {
public:
    std::string nombre;
    // 0: vida, 1: ataque, 2: defensa
    std::array<int, 3> estadisticas;

    Personaje(std::string n, int vida, int ataque, int defensa)
        : nombre(std::move(n)), estadisticas{vida, ataque, defensa} {
        std::cout << "Constructor: nace " << nombre << std::endl;
    }

    void imprimir() const {
        std::cout << "Personaje " << nombre
                  << " [Vida: " << estadisticas[0]
                  << ", ATK: " << estadisticas[1]
                  << ", DEF: " << estadisticas[2]
                  << "]" << std::endl;
    }
};

void simularEncuentro() {
    std::cout << "\n--- Iniciando encuentro ---" << std::endl;
    Personaje heroe("Aragorn", 100, 20, 15);

    // Copia segura (deep copy de valores, no de punteros):
    Personaje copiaHeroe = heroe;
    copiaHeroe.nombre = "Copia de Aragorn";

    heroe.imprimir();
    copiaHeroe.imprimir();

    std::cout << "Saliendo del encuentro..." << std::endl;
}

int main() {
    simularEncuentro();
    std::cout << "\nSimulación terminada." << std::endl;
    return 0;
}
```


El problema del código original era que usaba memoria dinámica sin liberarla, lo que causaba fugas, y además cuando se copiaba un personaje los dos quedaban compartiendo los mismos datos, lo que podía generar errores y fallos. Para solucionarlo cambié el arreglo con punteros por un arreglo normal dentro de la clase, así cada objeto guarda sus propios valores y no hay que preocuparse por liberar memoria. De esta forma el programa funciona más seguro, no se pierde memoria y las copias de personajes se hacen bien.
