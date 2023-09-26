<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 5 


package com.mycompany.vehiculo;  


       // Clase base: Vehiculo  

class Vehiculo {  
    protected String marca; // Cambiamos a protegido  
    protected String modelo; // Cambiamos a protegido  
    private int año;  

    public Vehiculo(String marca, String modelo, int año) {  
        this.marca = marca;  
        this.modelo = modelo;  
        this.año = año;  
    }  

    public void mostrarInformacion() {  
        System.out.println("Marca: " + marca);  
        System.out.println("Modelo: " + modelo);  
        System.out.println("Año: " + año);  
    }  

    public class Main {  
    public static void main(String[] args) {  
     
        Automovil automovil = new Automovil("Chevoret", "Blazzer", 2022, 4, "Automática");  

        System.out.println("Información del Automóvil:");  
        automovil.mostrarInformacionAutomovil();         
       
        Motocicleta motocicleta = new Motocicleta("BMW", "1200", 2021, "Deportiva", 1200);  
        
        System.out.println("\nInformación de la Motocicleta:");  
        motocicleta.mostrarInformacionMotocicleta();  
     
    }
   }
}

**Automovil**
class Automovil extends Vehiculo {  
    private int numPuertas;  
    private String tipoTransmision;  

    public Automovil(String marca, String modelo, int año, int numPuertas, String tipoTransmision) {  
        super(marca, modelo, año);  
        this.numPuertas = numPuertas;  
        this.tipoTransmision = tipoTransmision;  
    }

    public void mostrarInformacionAutomovil() {  
        mostrarInformacion();  
        System.out.println("Número de Puertas: " + numPuertas);  
        System.out.println("Tipo de Transmisión: " + tipoTransmision);  
    }
}

**Motocicleta**
class Motocicleta extends Vehiculo {  
    private String tipo;  
    private int cilindraje;  

    public Motocicleta(String marca, String modelo, int año, String tipo, int cilindraje) {  
        super(marca, modelo, año);  
        this.tipo = tipo;  
        this.cilindraje = cilindraje;  
    }  

    public void mostrarInformacionMotocicleta() {  
        mostrarInformacion();  
        System.out.println("Tipo de Motocicleta: " + tipo);  
        System.out.println("Cilindraje (cc): " + cilindraje);  
    }
}

