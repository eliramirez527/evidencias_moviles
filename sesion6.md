<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 6


package com.mycompany.moneda;

**//SUPER CLASE**

class Moneda {  
    private String nombre;  
    private String símbolo;  
    private String mercados;  

    public Moneda(String nombre, String símbolo, String mercados) {  
        this.nombre = nombre;  
        this.símbolo = símbolo;  
        this.mercados = mercados;  
    }

    public String getNombre() {  
        return nombre;  
    }  

    public void setNombre(String nombre) {  
        this.nombre = nombre;  
    }  

    public String getSímbolo() {  
        return símbolo;  
    }  

    public void setSímbolo(String símbolo) {  
        this.símbolo = símbolo;  
    }  

    public String getMercados() {  
        return mercados;  
    }  

    public void setMercados(String mercados) {  
        this.mercados = mercados;  
    }  

     public void mostrarInformacion() {  
        System.out.println("Nombre: " + nombre);  
        System.out.println("Simbolo: " + símbolo);  
        System.out.println("Mercado: " + mercados);  
     }  
}  

**//HIJA**

package com.mycompany.moneda;  

 public class usd extends Moneda {  
     
     private double precioDolar;  

    public usd(double precioDolar, String nombre, String símbolo, String mercados) {  
        super(nombre, símbolo, mercados);  
        this.precioDolar = precioDolar;  
    }  

    public double getPrecioDolar() {  
        return precioDolar;  
    }  

    public void setPrecioDolar(double precioDolar) {  
        this.precioDolar = precioDolar;  
    }  
             
     public void mostrar(){  
         super.mostrarInformacion();  
         System.out.println("La tendencia de los mercados para hoy es : " + precioDolar);  
 
    }  
 }  

**//HIJA**

package com.mycompany.moneda;  

 public class cad extends Moneda {  
     
     private double preciocanadiense;  

    public cad(double preciocanadiense, String nombre, String símbolo, String mercados) {  
        super(nombre, símbolo, mercados);  
        this.preciocanadiense = preciocanadiense;  
    }  

    public double getPreciocanadiense() {  
        return preciocanadiense;  
    }  

    public void setPreciocanadiense(double preciocanadiense) {  
        this.preciocanadiense = preciocanadiense;  
    }  
  
     public void mostrar(){  
         super.mostrarInformacion();  
         System.out.println("La tendencia de los mercados para hoy es : " + preciocanadiense);  
 
 
    }  
 }  

**//HIJA**

package com.mycompany.moneda;  

 public class mxm extends Moneda {  
     
     private double preciomexicano;  

    public mxm(double preciomexicano, String nombre, String símbolo, String mercados) {  
        super(nombre, símbolo, mercados);  
        this.preciomexicano = preciomexicano;  
    }  

    public double getPreciomexicano() {  
        return preciomexicano;  
    }  