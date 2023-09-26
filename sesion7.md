<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 7 


package com.mycompany.producto;

public class Producto {

    private String nombre;
    private double precio;
    private int cantidad;

    public Producto() {
        this.nombre = "Desconocido";
        this.precio = 0.00;
        this.cantidad = 0;
    }

    public Producto(String nombre, double precio) {
        this.nombre = nombre;
        this.precio = precio;
        this.cantidad = 0;
    }

    public Producto(String nombre, double precio, int cantidad) {
        this.nombre = nombre;
        this.precio = precio;
        this.cantidad = cantidad;
    }

    public double calcularValorTotal() {
        return this.precio * this.cantidad;
    }

    public void mostrarInformacion() {
        System.out.println("Informacion Producto");
        System.out.println("Nombre" + nombre);
        System.out.println("Precio" + precio);
        System.out.println("Cantidad" + cantidad);
        System.out.println("Valor tototal : $" + calcularValorTotal());
    }

    public void incrementarCantidad() {
        cantidad++;
    }

    public void incrementarCantidad(int cantidadIncrementar) {
        cantidad += cantidadIncrementar;
    }

    public void actualizarPrecio(double actualizarPrecio) {
        precio = 4500;
        System.out.println("El precio del dolar para el dia hoy es de $4.500");
    }

    public void actualizarPrecio(double nuevoPrecio, String moneda, double tasaCambio) {
        if (moneda.equals("4200")) {
            precio = nuevoPrecio * tasaCambio;
        } else if (moneda.equals("3800")) {
            precio = nuevoPrecio * tasaCambio;
        } else {
            System.out.println("Moneda no admitida");
        }
    }
    public static void main(String[] args) {        
        Producto producto1 = new Producto();
        Producto producto2 = new Producto("Producto 2", 10.0);
        Producto producto3 = new Producto("Producto 3", 20.0, 5);
      
        System.out.println("Información de Producto 1:");
        producto1.mostrarInformacion();

        System.out.println("\nInformación de Producto 2:");
        producto2.mostrarInformacion();

        System.out.println("\nInformación de Producto 3:");
        producto3.mostrarInformacion();
        
        producto1.incrementarCantidad();
        producto2.incrementarCantidad(3);
        producto3.actualizarPrecio(15.0);

        System.out.println("\nDespués de las operaciones:");

        System.out.println("\nInformación de Producto 1:");
        producto1.mostrarInformacion();

        System.out.println("\nInformación de Producto 2:");
        producto2.mostrarInformacion();

        System.out.println("\nInformación de Producto 3:");
        producto3.mostrarInformacion();
       
        producto1.actualizarPrecio(10.0, "Euro", 1.18);
        producto2.actualizarPrecio(10.0, "Peso Colombiano", 3875.0);

        System.out.println("\nDespués de actualizar los precios:");

        System.out.println("\nInformación de Producto 1:");
        producto1.mostrarInformacion();

        System.out.println("\nInformación de Producto 2:");
        producto2.mostrarInformacion();
    }

}
