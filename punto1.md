```mermaid
classDiagram
    class Libro {
        +String titulo
        +String ISBN
        +int año_publicacion
    }
    
    class Lector {
        +String numero_socio
        +String nombre
        +Date fecha_registro
    }
    
    class Prestamo {
        +Date fecha_prestamo
        +Date fecha_devolucion
    }
    
    Libro "1" --o "0..*" Prestamo : prestado_en
    Lector "1" --o "0..*" Prestamo : realiza
    Prestamo "0..*" -- "1" Libro : libro
    Prestamo "0..*" -- "1" Lector : lector
