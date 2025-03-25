# primer código
```mermaid
classDiagram
    class CuartoHotelero {
        - int identificador
        - string categoria
        - bool estaReservado
        + CuartoHotelero(int, string)
        + ~CuartoHotelero()
        + int obtenerIdentificador()
        + string obtenerCategoria()
        + bool verificarDisponibilidad()
        + void reservar()
        + void cancelarReserva()
    }

    class Huesped {
        - int documento
        - string nombreCompleto
        + Huesped(int, string)
        + ~Huesped()
        + int obtenerDocumento()
        + string obtenerNombreCompleto()
    }

    class Establecimiento {
        - string denominacion
        - vector<CuartoHotelero> listaCuartos
        - vector<Huesped*> listaHuespedes
        + Establecimiento(string)
        + ~Establecimiento()
        + void incluirCuarto(int, string)
        + void registrarHuesped(Huesped* nuevoHuesped)
        + void desplegarInformacion()
    }

    Establecimiento *-- CuartoHotelero
    Establecimiento o-- Huesped
