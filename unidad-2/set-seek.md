# Unidad 2

## 🔎 Fase: Set + Seek

### ACTIVIDAD 01

Escribe tu mismo ambos programas.
Simula paso a paso el programa en ensamblador. Recuerda la metodología: predice, ejecuta, observa y reflexiona.

R:

@SCREEN

M=1

### ACTIVIDAD 02

Escribe tu mismo los programas.
Simula paso a paso el programa ensamblador. Recuerda la metodología: predice, ejecuta, observa y reflexiona.

@SCREEN 
M= -1

EnC++:

screen = -1; //Forzar el compilador para que asigne la variable screen a la direccion: 16386

screen = 0xFFFF

### ACTIVIDAD 03

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

TRADUCCION

Screen= -1;
Contador= 0;




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


### ACTIVIDAD 05

```
int a = 10;
int* p;
p = &a;
*p = 20;
```
R:


```
int a = 10;
int b = 5;
int *p;
p = &a;
b = *p;
```
R:




