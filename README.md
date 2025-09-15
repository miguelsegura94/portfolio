# Miguel Angel Segura Perez

Desarrollador back-End buscando el primer trabajo como junior.


## Contacto
```text
✉️miguel.a.segura.94@gmail.com
```
[<img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" width="28" alt="LinkedIn"/>](https://www.linkedin.com/in/miguel-angel-segura-perez-78b537364/)
[![LinkedIn](https://img.shields.io/badge/Perfil-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/miguel-angel-segura-perez-78b537364/)  
[<img src="https://cdn-icons-png.flaticon.com/512/25/25231.png" width="28" alt="GitHub"/>](https://github.com/miguelsegura94)
[![GitHub](https://img.shields.io/badge/Perfil-black?style=for-the-badge)](https://github.com/miguelsegura94) 



## Sobre mí

Desarrollador **Back-End** con conocimientos en **SQL Server Management**, **APIs**, control de versiones con **Git** y **GitHub**,  
y realizando pruebas unitarias con **xUnit** para garantizar la calidad del código. También tengo experiencia en **Radzen Blazor** para crear interfaces y consumir APIs de manera eficiente.  

Capacidad de trabajar bajo objetivos, aprender con rapidez y adaptarme a nuevas tecnologías. Tengo un alto nivel en inglés.
Actualmente buscando mi primer trabajo como desarrollador de **Back-End** para seguir creciendo profesionalmente.


## Habilidades y herramientas

**Habilidades:**  
`C#`, `SQL`, `Entity Framework`, `Radzen Blazor`, `xUnit`, `ADO.NET`, `SOLID`, `ASP.NET Core Web API`  

**Principales Skills:**  
![C#](https://img.shields.io/badge/C%23-32325D?style=for-the-badge)
![SQL](https://img.shields.io/badge/SQL-00758F?style=for-the-badge)
![Radzen Blazor](https://img.shields.io/badge/Radzen-Blazor-blue?style=for-the-badge)
![xUnit](https://img.shields.io/badge/xUnit-FA5C5C?style=for-the-badge)

**Herramientas:**  
`Git`, `Visual Studio`, `Postman`, `Blazor`, `SQL Server Management Studio (SSMS)`  

**Herramientas destacadas:**  
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge)
![Visual Studio](https://img.shields.io/badge/Visual_Studio-5C2D91?style=for-the-badge&logo=visual-studio)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge)


## Proyectos

## **Aplicación de Gestión de Capturas de Pesca (Front-End y Back-End)** 

**Tecnologías:** `C#`, `Entity Framework Core`, `SQL Server`, `Radzen Blazor`, `xUnit`, `ADO.NET`, `Git`, `Postman`.

**Descripción**  
Aplicación de escritorio y web que permite gestionar capturas de pesca de forma completa, incluyendo usuarios, especies, tamaños y estilos de pesca. También permite realizar una búsqueda compleja en las captura que ya estan añadidas en la base de datos. Además de realizar el login/registro de usuarios. El proyecto incluye un **Back-End** en C# con API REST y un **Front-End** en Radzen Blazor, consumiendo la API para mostrar, añadir, editar y eliminar capturas de forma dinámica.

**Funciones implementadas**
- Gestión de capturas por usuarios, incluyendo alta, edición y eliminación.
- **Login seguro con contraseñas encriptadas** para cada usuario.
- **Búsqueda dinámica de capturas**, permitiendo filtrar rápidamente por cualquier atributo.
- Posibilidad de **añadir imágenes a las capturas** para un registro más visual.
- Validaciones de campos y tipos de datos antes de insertar registros en la base de datos.  
- Control de claves primarias y foráneas para mantener la integridad de la información.  
- Aplicación de los principios **SOLID** en la arquitectura del backend.

**Ejemplo de código (C#)**
```csharp
public async Task<Gestion> AñadirCapturaObligatorio(CapturaInsertObligatorio modeloCaptura)
{
    Gestion gestion = new Gestion();
    Captura captura = new Captura();
    try
    {
        bool usuarioExiste = _context.Usuarios.Any(u => u.Id == modeloCaptura.UsuarioId);
        if (!usuarioExiste)
        {
            gestion.setError("El usuario al que agregar la captura no existe.");
            return gestion;
        }
        if (string.IsNullOrWhiteSpace(modeloCaptura.NombreEspecie) || string.IsNullOrEmpty(modeloCaptura.NombreEspecie))
        {
            gestion.setError("El nombre no puede estar vacío.");
            return gestion;
        }
        if (!Enum.IsDefined(typeof(EstiloPesca), modeloCaptura.EstiloPesca))
        {
            gestion.setError("El estilo de pesca especificado no es válido.");
            return gestion;
        }
        if (modeloCaptura.Tamaño < 0)
        {
            gestion.setError("El tamaño no puede ser inferior a 0.");
            return gestion;
        }
        captura.UsuarioId = modeloCaptura.UsuarioId;
        captura.NombreEspecie = modeloCaptura.NombreEspecie;
        captura.Tamaño = modeloCaptura.Tamaño;
        captura.EstiloPesca = modeloCaptura.EstiloPesca;
        await _context.Capturas.AddAsync(captura);
        await _context.SaveChangesAsync();
        gestion.data = captura.CapturaId;
        gestion.Correct("Captura añadida correctamente");
    }
    catch (Exception ex)
    {
        gestion.setError("Error de tipo {0}, mensaje: {1}", new List<dynamic>() { ex.GetType().Name, ex.Message });
    }
    return gestion;
}
// Este método agrega una nueva captura pasando los datos obligatorios.
// Realiza varias validaciones: verifica que el usuario exista, que el nombre de la especie no esté vacío,
// que el estilo de pesca sea válido y que el tamaño sea correcto.
// Si todos los datos son correctos, guarda la captura en la base de datos usando Entity Framework Core
// y devuelve en `gestion` el id de la captura y un mensaje de funcionamiento correcto.
// En caso de error, devuelve en `gestion` el mensaje correspondiente.
```
**Enlace al proyecto:** [Ver en GitHub](https://github.com/miguelsegura94/AppPesca)

---

## **Gestión de base de datos en C# con SQL Server**  
**Tecnologías:** `C#`, `SQL Server`, `ADO.NET`, `Postman`, `Git`.

**Descripción**  
Aplicación de escritorio que permite gestionar tablas, columnas y registros de forma **genérica** en una base de datos. Implementa operaciones **CRUD** genéricas conectadas a una base de datos local y aplica los principios **SOLID**.

**Funciones implementadas**
- Inserción segura de registros con validaciones previas y por parámetros.
- Detección de claves primarias duplicadas.
- Verificación de claves foráneas antes del insert.
- Verificación del tipo de dato a implementar en la columna.
- Control de columnas autoincrementales y nulas.
- Comprobación si los caracteres son válidos.
- Documentación completa y detallada de todos los métodos.

**Ejemplo de código (C#)**
```csharp
if (!ExisteTabla(tablaBuscar, connectionString))
{
    gestion.setError($"Error: No existe la tabla {tablaBuscar}");
    return gestion;
}
// Este método verifica que existe la tabla antes de realizar ninguna gestión con ella,
// asegurando que no haya errores de SQL por referencias inexistentes
```
**Enlace al proyecto:** [Ver en GitHub](https://github.com/miguelsegura94/API)

---

## **Pokemon en aplicación de consola**  
**Tecnologías:** `C#`, `Git`, `Programación Orientada a Objetos (POO)`, `Consola de Windows`. 

**Descripción**  
Aplicación de consola que simula un combate por turnos entre dos jugadores al estilo Pokémon. Cada jugador dispone de un equipo de 3 Pokémon. El juego permite elegir habilidades, aplicar daño, usar curación, y manejar la lógica completa del combate hasta que uno de los jugadores gane. Lógica **reutilizable**.

**Funciones implementadas**
- Sistema de combate por turnos entre Jugador 1 y Jugador 2.
- Cada Pokémon cuenta con una lista de habilidades (daño o curación).
- Gestión de cálculo de daño según estadísticas.
- Control de salud, debilitamiento y cambio automático de Pokémon al ser derrotado.
- Verificación de habilidades seleccionadas y control de turnos.
- Soporte para habilidades de autoeliminación (por ejemplo, Id = 5 representa autodaño).
- Lógica clara y reutilizable basada en principios de buenas prácticas de programación.

**Ejemplo de código (C#)**
```csharp
if (Debilitado(PokemonQueDefiende))
{
    Console.Write($"{PokemonQueDefiende.Nombre} Debilitado.\n");
    PokemonQueDefiende.Debilitado = true;
    PokemonQueDefiende.Salud = 0;
    if (jugadores[otroJugador].EquipoDebilitado())
    {
        jugadores[otroJugador].HaGanado = true;
        Console.WriteLine($"Gana el {jugadores[especifico].Nombre}");
        return;
    }
    CambiarDebilitado(PokemonQueDefiende, jugadores, otroJugador);
}
//Este fragmento muestra cómo se comprueba si un Pokémon ha sido derrotado,
//cómo se actualiza su estado, y cómo se gestiona el flujo de combate tras una derrota.
```
**Enlace al proyecto:** [Ver en GitHub](https://github.com/miguelsegura94//pokemon-con-jugador1yjugador2)

---

## **Máquina expendedora**  
**Tecnologías:** `C#`, `Listas genéricas`, `lógica de negocio`, `consola`.  

**Descripción**  
Aplicación de consola que simula una máquina expendedora con productos y monedas. Permite ingresar dinero, seleccionar productos, mostrar saldo, añadir y eliminar productos **dinámicamente** y calcular cambio.

**Funciones implementadas**
- Gestión de productos con identificador, nombre y coste.
- Introducción y validación de monedas aceptadas (5, 10, 50 céntimos, 1€ y 2€).
- Compra de productos con devolución de cambio óptima en monedas.
- Menú interactivo con opciones para usuario.
- Añadir y eliminar productos a la máquina durante la ejecución.
- Manejo de errores como saldo insuficiente o producto inexistente.

**Ejemplo de código (C#)**
```csharp
public void ComprarProducto()
{
    VerProductos();
    Console.WriteLine("Diga el producto que desea comprar");
    int idComprar = int.Parse(Console.ReadLine());
    bool existe = ProductoExiste(idComprar);
    if (existe)
    {
        Producto productoAComprar = this.productos.FirstOrDefault(p => p.id.Equals(idComprar));
        if (this.suma >= productoAComprar.coste)
        {
            this.suma -= productoAComprar.coste;
            Console.WriteLine($"Aquí tiene su {productoAComprar.nombre}");
            Console.Write("Aquí tiene su cambio: ");
            CambioMonedas();
        }
        else
        {
            Console.WriteLine("No tiene suficiente saldo");
            Console.Write("Aquí tiene su devolución: ");
            CambioMonedas();
        }
    }
    else
    {
        Console.WriteLine("Ese producto no existe");
        Console.Write("Aquí tiene su dinero: ");
        CambioMonedas();
        VaciarDinero();
    }
}
// Este método permite al usuario seleccionar un producto de la máquina expendedora para su compra.
// Primero muestra el listado de productos disponibles, luego solicita al usuario que ingrese el ID del producto deseado.
// Verifica si el producto existe y si el saldo acumulado es suficiente para adquirirlo.
// Si el producto no existe, informa el error y devuelve el dinero al usuario.
// Si el usuario tiene saldo suficiente, el coste del producto se descuenta y se entrega el producto,
// además se calcula y devuelve el cambio correspondiente en monedas.
// Si el saldo es insuficiente, informa al usuario y devuelve todo el dinero insertado como cambio.
```
**Enlace al proyecto:** [Ver en GitHub](https://github.com/miguelsegura94//M-quina-expendedora)

---

## **3 en raya en consola**  
**Tecnologías:** `C#`, `Programación estructurada`, `Lógica en consola`.

**Descripción**  
Aplicación de consola que permite jugar una partida completa de 3 en raya entre dos jugadores. La lógica está programada para validar cada movimiento, mostrar el estado actual del tablero, y detectar automáticamente al ganador.

**Funciones implementadas**
- Tablero de juego representado con una matriz 3x3.
- Interfaz de consola para que ambos jugadores ingresen sus movimientos.
- Validación de coordenadas válidas y de que la casilla no esté ocupada.
- Detección automática del ganador (en filas, columnas o diagonales).
 -Finalización inmediata de la partida al detectar victoria.
- Visualización del tablero tras cada turno.

**Ejemplo de código (C#)**
```csharp
if (matriz[filaX, columnaX] == 'X' || matriz[filaX, columnaX] == 'O')
{
    Console.Write("La posición está ocupada\n");
    fichaXValido = false;
}
else
{
    matriz[filaX, columnaX] = 'X';
    fichaXValido = true;
    VerificarGanador('X');
}
// Este bloque asegura que no se pueda sobreescribir una celda ocupada,
// y llama a la función para comprobar si el jugador actual ha ganado.
```
**Enlace al proyecto:** [Ver en GitHub](https://github.com/miguelsegura94/3-en-raya)

---



