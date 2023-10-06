<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 8 

**Principal**


import java.util.ArrayList;  

public class principal {  

    public class Main {  

        public static void main(String[] args) {  
            System.out.println("");  
            System.out.println("*****Cancion****");  
            cancion cancion1 = new cancion("Rock");  
            cancion1.play();  
            cancion1.stop();  
            cancion1.pause();  
            cancion1.next();  
            cancion1.previus();  
            System.out.println();  

            System.out.println("");  
            System.out.println("*****Banda Sonora****");  
            bandaSonora banson = new bandaSonora("Rock", "Highlander");  
            banson.play();  
            banson.stop();  
            banson.pause();  
            banson.next();  
            banson.previus();  

            System.out.println();  
            System.out.println("*****Cancion****");  
            ArrayList<musica> canciones = new ArrayList<>();  
            canciones.add(new cancion("poison"));  
            canciones.add(new cancion("november"));  
            canciones.add(new cancion("nobody's fool"));  
            System.out.println(canciones);  
            album albu = new album("ArrayList", "Rock");  
            albu.play();  
            albu.stop();  
            albu.pause();  
            albu.next();  
            albu.previus();  
        }
    }

}

**Musica**

public abstract class musica{  
    private String titulo;  

    public musica(String titulo) {  
        this.titulo = "Rock";  
    }  

    public String getTitulo() {  
        return titulo;  
    }      
public abstract void play();  
public abstract void stop();  
public abstract void pause();  
public abstract void next();  
public abstract void previus();  
}

**Cancion** 

public class cancion extends musica {  

    private String artista;  
    private String album;  

    public cancion(String titulo) {  
        super(titulo);  
        this.artista = "Queen";  
        this.album = "A Night at the Opera";  
    }

    public String getArtista() {  
        return artista;  
    }

    public String getAlbum() {  
        return album;  
    }

    @Override  
    public void play() {  
        System.out.println("Reproducir cancion");  
    }

    @Override  
    public void stop() {  
        System.out.println("Detener cancion ");  
    }

    @Override  
    public void pause() {  
        System.out.println("Detener cancion ");  
    }

    @Override  
    public void next() {  
        System.out.println("Pausar la siguiente cancion");  
    }

    @Override  
    public void previus() {  
        System.out.println("Retrocer a la canción anterior ");  
    }

}

**Banda Sonora**

public class bandaSonora extends musica {  
    private String pelicula;

    public bandaSonora(String titulo, String pelicula) {  
        super(titulo);  
        this.pelicula = "Highlander";  
    }

    public String getPelicula() {  
        return pelicula;  
    }

    @Override  
    public void play() {  
        System.out.println("Reproducir anda sonora de la película: " );  
    }

    @Override  
    public void stop() {  
        System.out.println("Detener banda sonora de la película: " );  
    }

    @Override  
    public void pause() {  
        System.out.println("Päusa banda sonora ");  
    }

    @Override  
    public void next() {  
       System.out.println("Siguiente banda sonora ");  
    }

    @Override    
    public void previus() {  
       System.out.println("retroceder banda sonora ");   
    }
}

**Album**

import java.util.ArrayList;  

public class album extends musica {  

    private ArrayList<musica> canciones;  

    public album(String titulo, String rock) {  
        super(titulo);  
        this.canciones = canciones;  
    }

    public ArrayList<musica> getCanciones() {  
        return canciones;  
    }
      
    @Override  
    public void play() {  
        System.out.println("Reproduciendo");  
    }

    @Override  
    public void stop() {  
        System.out.println("Deteniendo");  
    }

    @Override  
    public void pause() {  
        System.out.println("Pausando");  
    }

    @Override  
    public void next() {  
        System.out.println("Avanzando");  
    }

    @Override  
    public void previus() {  
        System.out.println("Retrocediendo");  
    }

  }

