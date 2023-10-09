<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 8 

**Principal**

```java

import java.util.ArrayList;
import java.util.List;

public class principal {

    public static void main(String[] args) {

        cancion cancion1 = new cancion("Cancion 1", "Artista 1", "Album 1");
        cancion cancion2 = new cancion("Cancion 2", "Artista 2", "Album 2");

        bandaSonora bandaSonora1 = new bandaSonora("Banda Sonora 1", "Película 1");
        bandaSonora bandaSonora2 = new bandaSonora("Banda Sonora 2", "Película 2");

        List<cancion> cancionesAlbum = new ArrayList<>();
        cancionesAlbum.add(new cancion("Cancion A", "Artista X", "Album Y"));
        cancionesAlbum.add(new cancion("Cancion B", "Artista X", "Album Y"));
        cancionesAlbum.add(new cancion("Cancion C", "Artista X", "Album Y"));
        album album = new album("cancionesAlbum", "Album 1");

        cancion1.play();
        cancion1.pause();
        cancion1.next();
        cancion1.stop();
        cancion1.previus();
        cancion2.play();
        cancion2.pause();
        cancion2.next();
        cancion2.stop();
        cancion2.previus();

        bandaSonora1.play();
        bandaSonora1.pause();
        bandaSonora1.next();
        bandaSonora1.stop();
        bandaSonora1.previus();
        bandaSonora2.play();
        bandaSonora2.pause();
        bandaSonora2.next();
        bandaSonora2.stop();
        bandaSonora2.previus();

        album.play(); 
        album.pause();
        album.next();
        album.stop();
        album.previus();
     
    }
}
```

```java
**Musica**

package com.mycompany.musica;

public abstract class musica {

    private String titulo;

    public musica(String titulo) {
        this.titulo = titulo;
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

```

```java
**Cancion** 

package com.mycompany.musica;

public class cancion extends musica {

    private String artista;
    private String album;

    public cancion(String titulo, String artista, String album) {
        super(titulo);
        this.artista = artista;
        this.album = album;
    }

    public String getArtista() {
        return artista;
    }

    public String getAlbum() {
        return album;
    }

    @Override
    public void play() {
        System.out.println("Reproduciendo canción " + getTitulo() + " de " + artista + " del álbum " + album);
    }

    @Override
    public void stop() {
        System.out.println("Deteniendo canción " + getTitulo());
    }

    @Override
    public void pause() {
        System.out.println("Pausando canción " + getTitulo());
    }

    @Override
    public void next() {
        System.out.println("Avanzando a la siguiente canción");
    }
    @Override
    public void previus() {
        System.out.println("Retrocediendo a la canción anterior");

    }
}

```
```java
**Banda Sonora**

package com.mycompany.musica;


public class BandaSonora extends musica {
    private String pelicula;

    public BandaSonora(String titulo, String pelicula) {
        super(titulo);
        this.pelicula = pelicula;
    }

    @Override
    public void play() {
        System.out.println("Reproduciendo banda sonora de " + pelicula + " - " + getTitulo());
    }

    @Override
    public void stop() {
        System.out.println("Detener banda sonora de la película: " + pelicula);
    }

    @Override
    public void pause() {
        System.out.println("Pausando banda sonora de " + pelicula);
    }

    @Override
    public void next() {
       System.out.println("Avanzando a la siguiente canción de la banda sonora de " + pelicula);
    }

    @Override
    public void previus() {
       System.out.println("Retrocediendo a la canción anterior de la banda sonora de " + pelicula);
    }
}
```
```java
**Album**

package com.mycompany.musica;

import java.util.List;


public class album extends musica {
       private List<cancion> canciones;

    public album(String titulo, List<cancion> canciones) {
        super(titulo);
        this.canciones = canciones;
    }

  
    @Override
      public void play() {
        System.out.println("Reproduciendo álbum " + getTitulo());
        for (cancion cancion : canciones) {
            cancion.play();
    }
 }
    @Override
    public void stop() {
        System.out.println("Deteniendo álbum " + getTitulo());
        for (cancion cancion : canciones) {
            cancion.stop();
    }    
   }
    @Override
    public void pause() {
          System.out.println("Pausando álbum " + getTitulo());
        for (cancion cancion : canciones) {
            cancion.pause();
    }
  }
    @Override
    public void next() {
        System.out.println("Avanzando a la siguiente canción del álbum " + getTitulo());
        canciones.get(canciones.size() - 1).next();
    }
 
    @Override
    public void previus() {
        System.out.println("Retrocediendo a la canción anterior del álbum " + getTitulo());
      }  
    
}
```