# Unidad 3


## 🤔 Fase: Reflect

### ACTIVIDAD DE META COGNICION 
📤 Bitácora

IMPORTANTE: Responde todas las preguntas sin consultar tus apuntes, código previo, internet o herramientas de IA. La meta es el esfuerzo por recordar y aplicar, no la perfección.

Parte 1: recuperación de conocimiento (Retrieval Practice)

Explica con tus propias palabras qué es el stack y qué es el heap en C++.

Describe las tres formas de pasar parámetros a una función en C++ (valor, referencia y puntero). Para cada una, explica qué sucede en memoria y cuándo usarías cada método.

¿Qué diferencia hay entre una variable local, una variable global y una variable local estática? ¿En qué segmento del mapa de memoria se almacena cada una?

Explica qué es un objeto en C++ desde la perspectiva de memoria. ¿Dónde se almacenan los miembros de instancia y dónde los miembros estáticos?

Parte 2: transferencia y análisis de situación nueva

Imagina que trabajas en un equipo de desarrollo de videojuegos y tu compañero te muestra este código problemático que está causando crashes en el juego:


```
#include <iostream>
using namespace std;

class Enemigo {
public:
    static int totalEnemigos;
    int vida;
    int* armas;

    Enemigo(int v) : vida(v) {
        totalEnemigos++;
        armas = new int[3];
        armas[0] = 10; armas[1] = 15; armas[2] = 20;
    }
};

int Enemigo::totalEnemigos = 0;

void crearEscuadron() {
    for(int i = 0; i < 5; i++) {
        Enemigo soldado(100);
        soldado.vida -= 10;
    }
    cout << "Escuadrón creado. Total enemigos: " << Enemigo::totalEnemigos << endl;
}

int main() {
    crearEscuadron();
    crearEscuadron();
    return 0;
}
````


Análisis de problemas: identifica al menos dos problemas serios en este código relacionados con el manejo de memoria. Explica por qué cada uno es problemático.

Predicción de comportamiento: ¿Qué valor mostrará totalEnemigos después de ejecutar el programa? ¿Por qué ocurre esto?

Propuesta de solución: escribe una versión corregida de la clase Enemigo que solucione los problemas identificados. Explica brevemente cada cambio que hiciste.

Parte 3: reflexión metacognitiva

De todos los conceptos que exploraste en esta unidad (stack vs heap, paso de parámetros, ciclo de vida de objetos, etc.), ¿Cuál consideras que es el más crítico para evitar errores en programas reales? ¿Por qué?

¿Cómo cambió tu comprensión sobre lo que realmente es un “objeto” después de comparar C++ con C#? ¿Qué implicaciones prácticas tiene esta diferencia?

Si tuvieras que explicar a un compañero de semestres anteriores por qué es importante entender la gestión de memoria en programación, ¿Qué le dirías en máximo 3 oraciones?
