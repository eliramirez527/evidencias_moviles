<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 10 

**Ejercicio 1:**

```java
public class Pricipal {
     public static void main(String[] args) {
        Vehiculo coche = new coche();
        Vehiculo moto = new Moto();
        Vehiculo bicicleta = new Bicicleta();

        System.out.println("Comportamiento del coche:");
        coche.acelar();
        coche.frenar();
        coche.girar();

        System.out.println("\nComportamiento de la moto:");
        moto.acelar();
        moto.frenar();
        moto.girar();

        System.out.println("\nComportamiento de la bicicleta:");
        bicicleta.acelar();
        bicicleta.frenar();
        bicicleta.girar();
     }
}

```java

public abstract class Vehiculo{
    public abstract void acelar();
    public abstract void frenar();
    public abstract void girar();
    
    }
  ``` 
```java

public class Bicicleta extends Vehiculo {

   @Override
    public void acelar() {
        System.out.println("La Bicicleta esta acelerando. ");
    }

    @Override
    public void frenar() {
        System.out.println("La Bicicleta esta acelerando. ");
    }

    @Override
    public void girar() {
        System.out.println("La Bicicletaesta girando. ");
    }

}

``` 
``` java

public class Moto extends Vehiculo{

    @Override
    public void acelar() {
        System.out.println("La Moto esta acelerando. ");
    }

    @Override
    public void frenar() {
        System.out.println("La Moto esta acelerando. ");
    }

    @Override
    public void girar() {
        System.out.println("La Moto esta girando. ");
    }

}

``` 
``` java

public class coche extends Vehiculo {

    @Override
    public void acelar() {
        System.out.println("El coche esta acelerando. ");
    }

    @Override
    public void frenar() {
        System.out.println("El coche esta acelerando. ");
    }

    @Override
    public void girar() {
        System.out.println("El coche esta girando. ");
    }

}
``` 



