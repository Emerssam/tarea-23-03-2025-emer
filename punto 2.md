```mermaid
classDiagram
    class Vehiculo {
        - string matricula
        - string tipo
        - bool enUso
        + Vehiculo(string, string)
        + ~Vehiculo()
        + string obtenerMatricula()
        + string obtenerTipo()
        + bool estaDisponible()
        + void alquilar()
        + void retornar()
    }

    class Usuario {
        - int identificador
        - string nombreCompleto
        + Usuario(int, string)
        + ~Usuario()
        + int obtenerIdentificador()
        + string obtenerNombreCompleto()
    }

    class Reserva {
        - Usuario* arrendatario
        - Vehiculo* vehiculoAsignado
        - int periodo
        + Reserva(Usuario*, Vehiculo*, int)
        + ~Reserva()
    }

    class EmpresaAlquiler {
        - string denominacion
        - vector<Vehiculo*> flota
        - vector<Usuario*> clientes
        + EmpresaAlquiler(string)
        + ~EmpresaAlquiler()
        + void incluirVehiculo(Vehiculo* vehiculoPtr)
        + void registrarUsuario(Usuario* usuarioPtr)
        + void desplegarDatos() const
    }

    EmpresaAlquiler o-- Vehiculo
    EmpresaAlquiler o-- Usuario
    Reserva --> Usuario
    Reserva --> Vehiculo
