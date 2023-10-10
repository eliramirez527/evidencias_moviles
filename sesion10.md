<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 10 

**Ejercicio 1:**

**Vehiculo**

```java

package com.mycompany.AppVehiculo;


abstract class Vehiculo {
    public abstract void acelerar();
    public abstract void frenar();
    public abstract void girar();
}

package com.mycompany.AppVehiculo;

public class Bicicleta extends Vehiculo{

    @Override
    public void acelerar() {
       System.out.println("La bicicleta esta acelerando");
    }

    @Override
    public void frenar() {
         System.out.println("La bicicleta esta acelerando");
    }

    @Override
    public void girar() {
         System.out.println("La bicicleta esta acelerando");
    }
    
}

package com.mycompany.AppVehiculo;

public class Moto extends Vehiculo {

    @Override
    public void acelerar() {
        System.out.println("La moto esta acelerando");
    }

    @Override
    public void frenar() {
        System.out.println("La moto esta acelerando");
    }

    @Override
    public void girar() {
        System.out.println("La moto esta acelerando");
    }
    
}

package com.mycompany.AppVehiculo;

public class Coche extends Vehiculo{

    @Override
    public void acelerar() {
        System.out.println("El coche esta acelerando");
    }

    @Override
    public void frenar() {
        System.out.println("El coche esta frenando");
    }

    @Override
    public void girar() {
        System.out.println("El coche esta girando");
    }
    
}

public static void main(String[] args) {
        Vehiculo coc = new Coche();
        Vehiculo mot = new Moto();
        Vehiculo bici = new Bicicleta();

        System.out.println("");
        System.out.println("****El coche****");
        coc.acelerar();
        coc.frenar();
        coc.girar();

        System.out.println("");
        System.out.println("****La moto****");
        mot.acelerar();
        mot.frenar();
        mot.girar();

        System.out.println("");
        System.out.println("****La bicicleta****");
        bici.acelerar();
        bici.frenar();
        bici.girar();

        System.out.println("");
        System.out.println("****Fin de la operacion****");
    }
}

```
**Producto**

```java


package appproducto;

public abstract class Producto {
  public abstract double calcularPrecio();
  public abstract double calcularImpuesto();

  }

package appproducto;

public class Libro extends Producto {
private double precio;

    public Libro(double precio) {
        this.precio = precio;
    }

    @Override
    public double calcularPrecio() {
        return precio ;
    }

    @Override
    public double calcularImpuesto() {
        return precio *1.14;
    }

}


package appproducto;

public class CD extends Producto {
private double precio;

    public CD(double precio) {
        this.precio = precio;
    }

    @Override
    public double calcularPrecio() {
        return precio ;
    }

    @Override
    public double calcularImpuesto() {
       return precio * 1.16;
    }

}

package appproducto;


public class DVD extends Producto{
 private double precio;

    public DVD(double precio) {
        this.precio = precio;
    }

    @Override
    public double calcularPrecio() {
       return precio ;
    }

    @Override
    public double calcularImpuesto() {
        return precio * 1.19;
    }

}


package appproducto;

public class AppProducto {

    public static void main(String[] args) {
        Producto libro = new Libro(50.000);
        Producto cd = new Libro(45.500);
        Producto dvd = new Libro(98.500);

        System.out.println("");
        System.out.println("****Libro****");
        System.out.println("El precio del libro es: " + libro.calcularPrecio());
        System.out.println("El precio del libro con impouesto es: " + libro.calcularImpuesto());

        System.out.println("");
        System.out.println("****CD****");
        System.out.println("El precio del CD es: " + cd.calcularPrecio());
        System.out.println("El precio del CD con impouesto eses: " + cd.calcularImpuesto());

        System.out.println("");
        System.out.println("****DVD****");
        System.out.println("El precio del DVD es: " + dvd.calcularPrecio());
        System.out.println("El precio del DVD con impouesto es: " + dvd.calcularImpuesto());

        System.out.println("");
        System.out.println("****FIN DE OPERACION****");
    }

}
```

**Cuenta**
```java
package appcuenta;

public abstract class Cuenta {

    protected double saldo;

    public Cuenta(double saldo) {
        this.saldo = saldo;
    }

    public abstract void depositar(double cantidad);
    public abstract void retirar(double cantidad);
    public abstract double consultarSaldo();
    
}



package appcuenta;


public class CuentaCorriente extends Cuenta {

    public CuentaCorriente(double saldo) {
        super(saldo);
    }

     @Override
    public void depositar(double cantidad) {
        saldo += cantidad;
    }

    @Override
    public void retirar(double cantidad) {
        if (cantidad <= saldo) {
            saldo -= cantidad;
        } else {
            System.out.println("Saldo insuficiente para retirar");
        }
    }

    @Override
    public double consultarSaldo() {
        return saldo;
    }
}


package appcuenta;

class CuentaAhorro extends Cuenta {

    private double tasaInteres;

    public CuentaAhorro(double saldoInicial, double tasaInteres) {
        super(saldoInicial);
        this.tasaInteres = tasaInteres;
    }

    @Override
    public void depositar(double cantidad) {
        saldo += cantidad;
    }

    @Override
    public void retirar(double cantidad) {
        if (cantidad <= saldo) {
            saldo -= cantidad;
        } else {
            System.out.println("Saldo insuficiente para retirar la cantidad especificada.");
        }
    }

    @Override
    public double consultarSaldo() {
        return saldo;
    }

    public double calcularIntereses() {
        return saldo * tasaInteres;
    }
}


package appcuenta;

public class CuentaPlazo extends Cuenta {

    private int plazoDias;
    private double tasaInteres;

    public CuentaPlazo(int plazoDias, double tasaInteres, double saldo) {
        super(saldo);
        this.plazoDias = plazoDias;
        this.tasaInteres = tasaInteres;
    }

    @Override
    public void depositar(double cantidad) {
        saldo += cantidad;
    }

    @Override
    public void retirar(double cantidad) {
        System.out.println("No se puede retirar dinero antes del plazo de vencimiento.");
    }

    @Override
    public double consultarSaldo() {
        return saldo;
    }

    
    public double calcularIntereses() {
        return saldo * tasaInteres * (plazoDias / 365.0);
    }
}

package appcuenta;

public class AppCuenta {

    public static void main(String[] args) {
        CuentaCorriente cte = new CuentaCorriente(2000000);
        CuentaAhorro cuentahor = new CuentaAhorro(5000000, 0.15);
        CuentaPlazo cuentpla = new CuentaPlazo(180, 0.3, 2000000);

        cte.depositar(500.000);
        cte.retirar(200.000);
        cte.consultarSaldo();

        double saldoCuentaCorriente = cte.consultarSaldo();
        System.out.println("Saldo Cuenta Corriente: $ " + saldoCuentaCorriente);

        cuentahor.depositar(1500000);
        cuentahor.retirar(200.000);
        cuentahor.consultarSaldo();

        double saldoCuentaAhorro = cuentahor.consultarSaldo();
        double interesesCuentaAhorro = cuentahor.calcularIntereses();
        System.out.println("Saldo Cuenta de Ahorro: $ " + saldoCuentaAhorro);
        System.out.println("Intereses ganados Cuenta de Ahorro: $ " + interesesCuentaAhorro);

        double saldoCuentaPlazoFijo = cuentpla.consultarSaldo();
        double interesesCuentaPlazoFijo = cuentpla.calcularIntereses();
        System.out.println("Saldo de la cuenta Plazo Fijo: $ " + saldoCuentaPlazoFijo);
        System.out.println("Intereses ganados Plazo Fijo:$ " + interesesCuentaPlazoFijo);
        
        System.out.println("");
        System.out.println("*****Fin de Operacion****");
    }

}
```