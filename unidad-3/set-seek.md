# Unidad 3

## 🔎 Fase: Set + Seek

### ACTVIDAD 01

QUE HACE EL BREAKPOINT ?

R: sirven para detener el programa en el tiempo y poder observar que es lo que hace, y poder iniciar el programa desde cierto punto del programa para poder ejecutar experimentos

PARA QUE SE USA LA VENTANA DEPURACION AUTOS

R: Sirve para poder aprender como funcionan los programas mediante una herramienta de depuracion, que facilita el aprendisaje de un lenguaje como el de c++

### ACTIVIDAD DE INTEGRACION


A PREDICCION



Que se espera y que se espera cuando termina ?

R: se espera que en la salida se esperaque el valor de a inicie siendo 20 y pase a ser 30, que el valor de b sea 20 y pase a ser 30 y lo mismo con c.


Mapa conceptual

R:

![WhatsApp Image 2025-08-17 at 10 22 01 AM](https://github.com/user-attachments/assets/22ecc271-f579-4544-a7b6-4fc7ac240a44)


B VERIFICACION Y ANALISIS

Capturas de pantalla sobre el antes y despues del codigo

R:


<img width="1906" height="959" alt="image" src="https://github.com/user-attachments/assets/9666e12d-9242-48d3-94ee-eb4db2b35b3f" />

<img width="1917" height="990" alt="image" src="https://github.com/user-attachments/assets/663361b8-96f6-44c8-b3d8-202b3881277b" />

<img width="1915" height="985" alt="image" src="https://github.com/user-attachments/assets/04e71896-0502-4dcb-8470-c82226a21eeb" />

<img width="1912" height="979" alt="image" src="https://github.com/user-attachments/assets/a9727174-cad6-4b00-b152-0fd51eebac38" />

<img width="1916" height="987" alt="image" src="https://github.com/user-attachments/assets/0bf3dade-d08d-4de0-9e68-285b79b2b246" />

<img width="1842" height="932" alt="image" src="https://github.com/user-attachments/assets/e2cc301c-1235-4705-af22-8c39e5893436" />

<img width="1895" height="958" alt="image" src="https://github.com/user-attachments/assets/061259d4-d959-4221-85fe-8fd8e5ab694a" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/403604cb-7fe6-437a-b831-ae893a1d488a" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/393cab1c-cd33-4118-8844-877bfa36c27d" />











Los puntos claves que pude identificar y en donde estuvieron los breakpoints en la actividad fueron


1: int main donde se van declarando las variables


2: sumaPorValor donde se ejecuta a= a + 10 despues de copiar el valor de val_A que se hace con a= 20 en donde a termina siendo 30 y el Val_A sigue en 20


3: sumaPorReferencia en donde ahora a no es una copia de val_B si no que es una referencia y aqui fue donde me equivoque en mi prediccion en el Val_A porque pensaba que se modificaba, y ahora en b si el Val_B termina siendo 30


4: sumaPorPuntero ahora a contiene la direccio de Val_C como un puntero osea *a = 20 y despues como lo demas el Val_C termina siendo 30


5: ejecutarContador en donde se hace uso de contador estatico en las tres llamadas de ejecutarContador


en la primera llamada el contador estatico esta en 0, osea que se inicia


en la segunda llamada se incrementa el comtador estatico a 1


en la tercera llamada se incrementa el contador a 2



Comparacion entre prediccion y resultado

R: A diferencia de uno casi todo fue lo mismo que lo que predije, me equivoque en el primer valor osea el de a que no cambia, y se esperaba que a diferencia de esto, que todo fuera igual porque por lo que veo el programa no depende de nada externo asi que no tendria que cambiar segun yo.

DIferencia entre una variable local normal y una estatica

R: una variable local normal vive en la memoria que al momento de ejecutar la funcion se crea pero al momento de salir de ella se destruye automaticamente, a diferencia de una variable local estatica que contador estatico esta dentro de ejecutarcontador que es una static por lo cual al momento de llamarla esta recuerda su valor ya que al ser estatica no se borra por eso es que el contador puede incrementar de 0 a 1 a 2 a 3 y asi si la seguimos llamando mas veces.


