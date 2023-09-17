<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 3 


**DESARROLLO**

**// ATRIBUTOS**

public class Jugadores {

  
  private String nombre;  
  private int edad;  
  private String posicion;  
  private int numero_camiseta;  
  private String equipo;  
  
**//CONSTRUCTORES**

  public Jugadores(String nombre, int edad, String posicion, int numero_camiseta, String equipo) {  
    this.nombre = nombre;  
    this.edad = edad;  
    this.posicion = posicion;  
    this.numero_camiseta = numero_camiseta;  
    this.equipo = equipo;  
  }
  
**//METODOS GETTER Y SETTER**

  public String getNombre() {   
    return nombre;    
  }

  public void setNombre(String nombre) {  
    this.nombre = nombre;  
  }  

  public int getEdad() {  
    return edad;  
  }  

  public void setEdad(int edad) {   
    this.edad = edad;   
  }  

  public String getPosicion() {   
    return posicion;    
  }  

  public void setPosicion(String posicion) {   
    this.posicion = posicion;  
  }  

  public int getNumero_camiseta() {  
    return numero_camiseta;  
  }  

  public void setNumero_camiseta(int numero_camiseta) {      
    this.numero_camiseta = numero_camiseta;  
  }  

  public String getEquipo() {  
    return equipo;  
  }  

  public void setEquipo(String equipo) {   
    this.equipo = equipo;  
  }  

**//METODOS**

  public String toString() {  
    return "Jugadores{" +  
        "nombre='" + nombre + '\'' +  
        ", edad=" + edad +  
        ", posicion='" + posicion + '\'' +  
        ", numero_camiseta=" + numero_camiseta +   
        ", equipo='" + equipo + '\'' +   
        '}';   
  }  

}

**//DIAPOSITIVA**

[Texto del enlace](https://drive.google.com/drive/folders/1xhXoN0igND6-2fsVVFBmnp9HQPVlO-gI)

