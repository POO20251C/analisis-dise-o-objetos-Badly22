```mermaid
classDiagram
    class ObraDeArte {
        +String titulo
        +String id_obra
        +Date fecha_creacion
    }

    class Artista {
        +String id_artista
        +String nombre
        +Date fecha_registro
    }

    class Exposicion {
        +Date fecha_exposicion
        +String estado
    }

    Artista "1" --o "0..*" ObraDeArte : crea
    ObraDeArte "1" --o "0..*" Exposicion : exhibida_en
    Artista "1" --o "0..*" Exposicion : participa
    Exposicion "0..*" -- "1" ObraDeArte : obra
    Exposicion "0..*" -- "1" Artista : artista
