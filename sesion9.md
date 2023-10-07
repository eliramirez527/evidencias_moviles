<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 9 

**AppConversor**  
<


```java

package com.mycompany.appconversor;
public class AppConversor {  

    public static void main(String[] args) {  

         System.out.println("");  
        System.out.println("**********Temperatura*********");  
        Temperatura t1 = new Temperatura("Celsius", "Fahrenheit");  
        Temperatura t2 = new Temperatura("Fahrenheit", "Celsius");  
        Temperatura t3 = new Temperatura("Celsius", "Kelvin");  
        Temperatura t4 = new Temperatura("Kelvin", "Celsius");  
        Temperatura t5 = new Temperatura("Fahrenheit", "Kelvin");  
        Temperatura t6 = new Temperatura("Kelvin", "Fahrenheit");  
        double res = t1.convertir(2);  
        System.out.println("De Celsius a Fahrenheit " + res);  
        res = t2.convertir(10);  
        System.out.println("De Fahrenheit a Celsius " + res);  
        res = t3.convertir(15);  
        System.out.println("De Celsius a Kelvin " + res);  
        res = t4.convertir(20);  
        System.out.println("De Kelvin a Celsius " + res);  
        res = t5.convertir(23);  
        System.out.println("De Fahrenheit a Kelvin " + res);  
        res = t6.convertir(10);  
        System.out.println("De Kelvin a Fahrenheit " + res);  


        System.out.println("");  
        System.out.println("**********Longitud*********");  
        Longitud l1 = new Longitud("Metros", "Pies");  
        Longitud l2 = new Longitud("Pies", "Metros");  
        Longitud l3 = new Longitud("Kilómetros", "Millas");  
        Longitud l4 = new Longitud("Millas", "Kilómetros");  
        res = l1.convertir(2.);  
        System.out.println("De metros a pies " + res);  
        res = l2.convertir(12.);  
        System.out.println("De pies a metros " + res);  
        res = l3.convertir(15.);  
        System.out.println("De Kilómetros a millas " + res);  
        res = l4.convertir(25.);  
        System.out.println("De millas a Kilómetros " + res);  

        System.out.println("");  
        System.out.println("**********Peso*********");  
        Peso p1 = new Peso("kilogramos", "libras");  
        Peso p2 = new Peso("libras", "kilogramos");  
        Peso p3 = new Peso("gramos", "libras");  
        Peso p4 = new Peso("libras", "gramos");  
        res = p1.convertir(50);  
        System.out.println("De Kilogramos a libras " + res);  
        res = p2.convertir(200);  
        System.out.println("De libras a Kilómetros " + res);  
        res = p3.convertir(100);  
        System.out.println("De gramos a libras " + res);  
        res = p4.convertir(250);  
        System.out.println("De libras a gramos " + res);  

        System.out.println("");  
        System.out.println("**********Divisas*********");  
        Divisas d1 = new Divisas("USDT", "EURO");  
        Divisas d2 = new Divisas("EURO", "USDT");  
        Divisas d3 = new Divisas("USDT", "COP");  
        Divisas d4 = new Divisas("COP","USDT");  
         res = d1.convertir(300);  
        System.out.println("De USDT a EURO " + res);  
        res = d2.convertir(1000);  
        System.out.println("De EURO a USDT " + res);  
        res = d3.convertir(500);  
        System.out.println("De USDT a COP " + res);  
        res = d4.convertir(250000);  
        System.out.println("De COP a USDT " + res);  
        

        System.out.println("");  
        System.out.println("**********Binarios*********");  
        binario b1 = new binario("decimal", "binario");  
        binario b2 = new binario("binario", "decimal");  
        binario b3 = new binario("decimal", "hexadecimal");  
        binario b4 = new binario("hexadecimal", "decimal");  
        res = b1.convertir(34);  
        System.out.println("De decimal a binario " + res);  
        res = b2.convertir(100010);  
        System.out.println("De binario a decimal " + res);  
        res = b3.convertir(25);  
        System.out.println("De decimal a hexadecimal " + res);  
        res = b4.convertir(19);  
        System.out.println("De hexadecimal a decimal " + res);  
        
        System.out.println("");  
        System.out.println("**********Fin de la operacion*********");  

    }  
}  
```
```java
**Conversor**  

package com.mycompany.appconversor;  


public abstract class Conversor {  
    protected String unidadOrigen;  
    protected String unidadDestino;  

    public Conversor(String unidadOrigen, String unidadDestino) {  
        this.unidadOrigen = unidadOrigen;  
        this.unidadDestino = unidadDestino;  
    }  
    public abstract double convertir(double cantidad);     
    
}  
```

```java

**Temperatura**  

public class Temperatura extends Conversor {  

    public Temperatura(String unidadOrigen, String unidadDestino) {  
        super(unidadOrigen, unidadDestino);  
    }  

    @Override  
    public double convertir(double cantidad) {  
        if (unidadOrigen.equals("Celsius") && unidadDestino.equals("Fahrenheit")) {  
            // Celsius a Fahrenheit  
            return (cantidad * 9 / 5) + 32;  
        } else if (unidadOrigen.equals("Fahrenheit") && unidadDestino.equals("Celsius")) {  
            // Fahrenheit a Celsius  
            return (cantidad - 32) * 5 / 9;  
        } else if (unidadOrigen.equals("Celsius") && unidadDestino.equals("Kelvin")) {  
            // Celsius a Kelvin  
            return cantidad + 273.15;  
        } else if (unidadOrigen.equals("Kelvin") && unidadDestino.equals("Celsius")) {  
            // Kelvin a Celsius  
            return cantidad - 273.15;  
        } else if (unidadOrigen.equals("Fahrenheit") && unidadDestino.equals("Kelvin")) {  
            // Fahrenheit a Kelvin  
            double celsius = (cantidad - 32) * 5 / 9;  
            return celsius + 273.15;  
        } else if (unidadOrigen.equals("Kelvin") && unidadDestino.equals("Fahrenheit")) {  
            // Kelvin a Fahrenheit  
            double celsius = cantidad - 273.15;  
            return (celsius * 9 / 5) + 32;  
        } else {  
            throw new IllegalArgumentException("Unidades de temperatura no compatibles");  
        }  
    }  
}  
```

```java
**Longitud**  

public class Longitud extends Conversor {  

    public Longitud(String unidadOrigen, String unidadDestino) {  
        super(unidadOrigen, unidadDestino);  
    }  

    @Override  
public double convertir(double cantidad) {  
    if (unidadOrigen.equals("Metros") && unidadDestino.equals("Pies")) {  
        return cantidad * 3.28084;  
    } else if (unidadOrigen.equals("Pies") && unidadDestino.equals("Metros")) {  
        return cantidad / 3.28084;  
    } else if (unidadOrigen.equals("Kilómetros") && unidadDestino.equals("Millas")) {  
        return cantidad * 0.621371;  
    } else if (unidadOrigen.equals("Millas") && unidadDestino.equals("Kilómetros")) {  
        return cantidad / 0.621371;  
    } else {  
        throw new IllegalArgumentException("Unidades de longitud no compatibles");  
    }  
   }  
}  
```

```java
**Peso**

public class Peso extends Conversor {  

    public Peso(String unidadOrigen, String unidadDestino) {  
        super(unidadOrigen, unidadDestino);  
    }  

    @Override  
public double convertir(double cantidad) {  
    if (unidadOrigen.equals("kilogramos") && unidadDestino.equals("libras")) {  
        return cantidad * 2.20462;  
    } else if (unidadOrigen.equals("libras") && unidadDestino.equals("kilogramos")) {  
        return cantidad / 2.20462;  
    } else if (unidadOrigen.equals("gramos") && unidadDestino.equals("libras")) {  
        return cantidad * 453.59237;  
    } else if (unidadOrigen.equals("libras") && unidadDestino.equals("gramos")) {              
        return cantidad  / 453.59237;  
    } else {  
        throw new IllegalArgumentException("Unidades de peso no compatibles");  
    }  
  }  
}  
```

```java
**Divisas**

 public class Divisas extends Conversor{  

    public Divisas(String unidadOrigen, String unidadDestino) {  
        super(unidadOrigen, unidadDestino);  
    }

    @Override  
    public double convertir(double cantidad) {  
        if (unidadOrigen.equals("USDT") && unidadDestino.equals("EURO")) {             
            return cantidad * 0.85;     
        } else if (unidadOrigen.equals("EURO") && unidadDestino.equals("USDT")) {              
            return cantidad / 0.85;   
        } else if (unidadOrigen.equals("USDT") && unidadDestino.equals("COP")) {             
            return cantidad * 4000.0;    
        } else if (unidadOrigen.equals("COP") && unidadDestino.equals("USDT")) {              
            return cantidad / 4000.0;    
        } else {  
            throw new IllegalArgumentException("Unidades de conversión no compatibles");  
        }  
    }  
}  
```

```java
**Binarios**

public class binario extends Conversor {  

    public binario(String unidadOrigen, String unidadDestino) {  
        super(unidadOrigen, unidadDestino);  
    }
 public String decimalToBinary(int decimalNumber) {  
        return Integer.toBinaryString(decimalNumber);  
    }  

    public int binaryToDecimal(String binaryNumber) {  
        return Integer.parseInt(binaryNumber, 2);  
    }  

    public String decimalToHexadecimal(int decimalNumber) {  
        return Integer.toHexString(decimalNumber);  
    }  

    public int hexadecimalToDecimal(String hexadecimalNumber) {  
        return Integer.parseInt(hexadecimalNumber, 16);  
    }         
  
    @Override  
    public double convertir(double cantidad) {  
    if (unidadOrigen.equals("decimal") && unidadDestino.equals("binario")) {  
            return Double.parseDouble(decimalToBinary((int) cantidad));  
        } else if (unidadOrigen.equals("binario") && unidadDestino.equals("decimal")) {  
            return binaryToDecimal(String.valueOf((int) cantidad));  
        } else if (unidadOrigen.equals("decimal") && unidadDestino.equals("hexadecimal")) {  
            return Double.parseDouble(decimalToHexadecimal((int) cantidad));  
        } else if (unidadOrigen.equals("hexadecimal") && unidadDestino.equals("decimal")) {  
            return hexadecimalToDecimal(String.valueOf((int) cantidad));  
        } else {  
            throw new IllegalArgumentException("Unidades de conversión no compatibles");  
        }  
     }  
}
```

    