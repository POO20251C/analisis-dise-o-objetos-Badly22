```mermaid
classDiagram
    class Habitacion {
        +String numero
        +String tipo
        +float tarifa_por_noche
    }

    class Huesped {
        +String id_huesped
        +String nombre
        +Date fecha_registro
    }

    class Reserva {
        +Date fecha_inicio
        +Date fecha_fin
        +String estado
    }

    Habitacion "1" --o "0..*" Reserva : reservada_en
    Huesped "1" --o "0..*" Reserva : realiza
    Reserva "0..*" -- "1" Habitacion : habitacion
    Reserva "0..*" -- "1" Huesped : huesped
