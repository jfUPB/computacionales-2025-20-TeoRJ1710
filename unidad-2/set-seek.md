# Unidad 2

## 🔎 Fase: Set + Seek

### ACTIVIDAD 01

Escribe tu mismo ambos programas.
Simula paso a paso el programa en ensamblador. Recuerda la metodología: predice, ejecuta, observa y reflexiona.

R:
```
@SCREEN       
D=A           
@addr
M=D           

@32768       
D=A           
@addr
A=M           
M=D           
(END)
@END
0;JMP   
```
traduccion a c++

```
#include <iostream>
#include <vector>
using namespace std;

const int SCREEN_ADDRESS = 16384;
vector<int> memory(32768); 

int main() {
    int addr = SCREEN_ADDRESS;      
    memory[addr] = 32768;           
}
```




### ACTIVIDAD 02

Escribe tu mismo los programas.
Simula paso a paso el programa ensamblador. Recuerda la metodología: predice, ejecuta, observa y reflexiona.
```
@SCREEN 
M= -1

EnC++:

screen = -1; //Forzar el compilador para que asigne la variable screen a la direccion: 16386

screen = 0xFFFF
```
### ACTIVIDAD 03
```
@SCREEN
M=-1
@CONTADOR
M=0

(LEER)

@24576
D=M
@100
D=D-A
@DERECHA
D;JEQ

@24576
D=M
@105
D=D-A
@IZQUIERDA
D;JEQ

@LEER
0;JMP



(DERECHA)

//BORRO LA DIRECCION ACTUAL

@CONTADOR
D=M
@SCREEN
A=D+A
M=0

//
@CONTADOR
M=M+1
D=M
@SCREEN
A=D+A
M=-1

@LEER
0;JMP

(IZQUIERDA)

@CONTADOR
D=M
@SCREEN
A=D+A
M=0


@CONTADOR
M=M-1
D=M
@SCREEN
A=D+A
M=-1

@LEER
0;JMP
````

TRADUCCION

```
#include <iostream>
#include <vector>

using namespace std;

const int SCREEN = 16384;
const int KBD = 24576;
vector<int> memory(32768); 

int main() {
    int contador = 0; 

    while (true) {
        int tecla = memory[KBD]; 

        if (tecla == 100) {
            memory[SCREEN + contador] = 0;
            contador++;
            memory[SCREEN + contador] = -1;
        }

       
        else if (tecla == 105) {
           
            memory[SCREEN + contador] = 0;
            contador--;
            memory[SCREEN + contador] = -1;
        }
        if (contador < 0 || contador > 511) break; // límite de pantalla horizontal
    }

    return 0;
}
```



### ACTIVIDAD 04

1:
```
//Adds 1+...+100.
int sum=0;
for(int i = 1; i <=100; i++){
   sum+= i;
}
```
TRADUCCION:
```
@0
D=A
@17
M=D

// i = 1
@1
D=A
@16
M=D

(LOOP)
  
    @16
    D=M
    @100
    D=D-A
    @END
    D;JGT     // Si i > 100 → saltar a END

    // sum += i
    @16
    D=M
    @17
    M=D+M

    // i++
    @16
    M=M+1

    @LOOP
    0;JMP

(END)
```

### ACTIVIDAD 05

```
int a = 10;
int* p;
p = &a;
*p = 20;
```
R:

````
@10
D=A
@16
M=D


@16
D=A
@17
M=D


@20
D=A      
@17
A=M      
M=D     
````



```
int a = 10;
int b = 5;
int *p;
p = &a;
b = *p;
```
R:

````
@10
D=A
@16
M=D


@5
D=A
@17
M=D


@16
D=A
@18
M=D


@18
A=M     
D=M      
@17
M=D      
````



