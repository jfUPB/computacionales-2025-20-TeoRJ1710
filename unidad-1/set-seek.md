# Unidad 1

## 🔎 Fase: Set + Seek

### Actividad 01

``` asm
(START)
@1
D=A
@2
D=D+A
(AQUI)
@16
M=D
@START
(END)
1;JMP
```

El programa en el que desarrollamos esta actividad el dia de hoy desarrolla segun ordenes y amacena datos en la memoria ram los cuales se pueden usar para darle ciertas ordenes para obtener resultados distintos, aqui se almacena el numero 1 en A ya que asi esta creada e programa, despues almacena el mismo resultado de A en D, despues le asigna un 2 a A, y suma los numeros que hay en A y en D y lo almacena en D, despues le asigna a A el numero 16 y almacena D en la memoria, y vuelve y se devuelve con el JMP

### Actividad 02

1. Identifica una instrucción que use la ALU y explica qué hace.

R: D= D-A Esta instrucción usa la ALU para restar el valor de A al valor de D, y el resultado se guarda en D, y despues se calcula cuántas posiciones se ha avanzado desde el inicio de la pantalla, restando la dirección SCREEN del valor actual de i. La ALU hace esa resta.

2. ¿Para qué sirve el registro PC?
3. 
R: El registro PC guarda la dirección de la siguiente instrucción que debe ejecutar la CPU cada vez que una instrucción se ejecuta el PC se actualiza para apuntar a la siguiente a menos que haya un salto que modifique el PC directamente y cambia el flujo del programa.

4. ¿Cuál es la diferencia entre @i y @READKEYBOARD?
   
R: basicamente i es una variable y el otro no, i es una variable que guarda la posicion actual que se va escrbir o borrar en la memoria de video, y la otra es una etiqueta que marca una posicion para poder hacer saltos y cumple su funcion para que se de el bucle

6. Describe qué se necesita para leer el teclado y mostrar información en la pantalla.
   
R: para leer el teclado y poder mostrar algo de esa accion el programa necesita al KDB, evaluar si hay una tecla presionada o no con el D;JNE y escribir en la memoria de la pantalla usando una variable como i.

8. Identifica un bucle en el programa y explica su funcionamiento.
   
R: Como dije en un anterior punto el @READKEYBOARD junto con el 0;JMP son el principal bucle del programa que hace que se repita una y otra vez

10. Identifica una condición en el programa y explica su funcionamiento.
    
R: y tambien como dije en un punto pasado una condicion como el D;JNE cumple con la funcion que si hay alguna tecla presionada, el programa salta a la parte donde escribe en pantalla.
