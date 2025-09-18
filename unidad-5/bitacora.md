# Bitácora de aprendizaje de la unidad 5

## 1.  **Diagnóstico inicial**

1: ¿Qué es el encapsulamiento para ti? Describe una situación en la que te haya sido útil o donde hayas visto su importancia.

R:  es el principio de agrupar datos (atributos) y los métodos que operan sobre ellos dentro de una única unidad (una clase) y controlar el acceso a esos datos para proteger su integridad y seguridad.

¿Qué es la herencia? ¿Por qué un programador decidiría usarla? Da un ejemplo simple.

R: la herencia es el metodo mediante por ejemplo el hijo puede como dice su nombre heredar los atributos o metodos de su padre ya existente, esto se puede utilizar de varias maneras como para organizacion del codigo, como para extender y darle mas funciones al codigo, para que sea mas compacto, etc.

¿Qué es el polimorfismo? Describe con tus palabras qué significa que un código sea “polimórfico”.

R: es como la capacidad que tiene un codigo de tratar o ordenar ciertas funciones para utilizarlas todas en una interfaz comun, sirve mas que todo para ordenaqr y compactar y que no se tenga que recurrir a muchas interfaces.

Parte 2: análisis de código (en C#)

````
using System;
using System.Collections.Generic;

public abstract class Figura
{
    private string nombre;

    public string Nombre
    {
        get { return nombre; }
        protected set { nombre = value; }
    }

    public Figura(string nombre)
    {
        this.Nombre = nombre;
    }

    public abstract void Dibujar();
}

public class Circulo : Figura
{
    public double Radio { get; private set; }

    public Circulo(double radio) : base("Círculo")
    {
        this.Radio = radio;
    }

    public override void Dibujar()
    {
        Console.WriteLine($"Dibujando un {Nombre} de radio {Radio}.");
    }
}

public class Rectangulo : Figura
{
    public double Base { get; private set; }
    public double Altura { get; private set; }

    public Rectangulo(double b, double h) : base("Rectángulo")
    {
        this.Base = b;
        this.Altura = h;
    }

    public override void Dibujar()
    {
        Console.WriteLine($"Dibujando un {Nombre} de {Base}x{Altura}.");
    }
}

public class Programa
{
    public static void Main()
    {
        List<Figura> misFiguras = new List<Figura>();

        misFiguras.Add(new Circulo(5.0));
        misFiguras.Add(new Rectangulo(4.0, 6.0));
        misFiguras.Add(new Circulo(10.0));

        foreach (Figura fig in misFiguras)
        {
            fig.Dibujar();
        }
    }
}
````

ENCAPSULAMIENTO:

````
public string Nombre
    {
        get { return nombre; }
        protected set { nombre = value; }
    }
````

R:  es un claro ejemplo de encapsulamiento porque proteje el acceso a NOMBRE, tambien permite leer desde afuera con el get pero n modificarlo


HERENCIA:

````
public class Circulo : Figura
````
Aqui se ve como la clse circulo hereda los atributos y las funciones de la clase figura


POLIMORFISMO:

````
 foreach (Figura fig in misFiguras)
        {
            fig.Dibujar();
        }
````
El polimorfismo hace que se pueda hacer que por ejemplo la variable fig cumpla distintas funciones dependiendo de lo que se le pide o que haga lo que se necesite segun el objeto


## 2.  **La pregunta inicial**

¿ Que es el encapsulamiento ? de que maneras se puede utilizar y como puedo aplicarlo de manera util en mi programa

## 3.  **Registro de exploración:** 

### Actividad 2

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/13da1781-f2f6-49cd-8c28-3a95101b6e07" />
Aqui pude identificar en el momento en donde se crea una particular en si su posicion y color

<img width="1920" height="1076" alt="image" src="https://github.com/user-attachments/assets/b2aa263f-c9a9-445a-bd26-4a5b2c95c8fe" />
En la siguiente linea pude observar como  cambia la position y velocity

<img width="1920" height="1012" alt="image" src="https://github.com/user-attachments/assets/ef2e11e0-7bb5-4424-8327-46a5835570c0" />
Aqui se ve cuando ocurre la explosion exitosamente

<img width="1917" height="1040" alt="image" src="https://github.com/user-attachments/assets/70cddb15-d679-47b7-bb3e-894cc63e22a2" />
Aqui se ve como nuevas particulas se agregan al vector

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c26a049b-0d06-4154-9f95-468beacbb70a" />
Aqui pude ver como diferentes clases se dibujan con diferentes formas


## 4.  **Consolidación, autoevaluación y cierre:**
> [!CAUTION]
> Esta sección es OBLIGATORIA y central para tu evaluación
