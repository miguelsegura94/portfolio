# Miguel Angel Segura Perez

Desarrollador back-End buscando el primer trabajo como junior.


#### Contacto
```typescript
 {
  email: "miguel.a.segura.94@gmail.com",
  linkedin: "https://www.linkedin.com/in/miguel-angel-segura-perez-78b537364/",
  github: "https://github.com/miguelsegura94",
}
```

#### Sobre mi
```typescript
"Desarrollador Back-End con conocimientos en SQL server management, APIs, control de versiones con Git y GitHub,"
"y realizando pruebas unitarias con xUnit para garantizar la calidad del código. Capacidad de trabajar bajo objetivos,"
"aprender con rapidez y adaptarme a nuevas tecnologías. Tengo un alto nivel en inglés."
"Actualmente buscando mi primer trabajo como desarrollador de back-end para seguir creciendo profesionalmente."
```

#### Habilidades y herramientas
```typescript
Habilidades: ["C#", "SQL", "Entity Framework", "Radzen", "xUnit", "Ado.Net", "SOLID", "ASP.NET Core Web API"]
Herramientas: ["Git", "Visual Studio", "Postman", "Blazor","SQL Server Management Studio (SSMS)"]
```
#### Proyectos

## **Gestión de base de datos en C# con SQL Server**  
**Tecnologías:** `C#`, `SQL Server`, `ADO.NET`, `Postman`, `Git`  

**Descripción**  
Aplicación de escritorio que permite gestionar tablas, columnas y registros de forma genérica en una base de datos. Implementa operaciones CRUD genéricas conectadas a una base de datos local y aplica los principios SOLID.

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

## **Pokemon en aplicación de consola**  
**Tecnologías:** `C#`, `Git`, `Programación Orientada a Objetos (POO)`, `Consola de Windows`. 

**Descripción**  
Aplicación de consola que simula un combate por turnos entre dos jugadores al estilo Pokémon. 
Cada jugador dispone de un equipo de 3 Pokémon. 
El juego permite elegir habilidades, aplicar daño, usar curación, y manejar la lógica completa del combate hasta que uno de los jugadores gane.

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

#### Experience
```typescript
experience: [
  {
    company: "Company Name",
    title: "Your Job Title",
    dateRange: "Jan 2022 - Present",
    bullets: [
      "Led development of microservices architecture serving 1M+ users",
      "Reduced API response times by 40% through optimization",
      "Mentored team of 5 junior developers",
    ],
  }
]
```

#### Education
```typescript
education: [
  {
    school: "University Name",
    degree: "Bachelor of Science in Computer Science",
    dateRange: "2014 - 2018",
    achievements: [
      "Graduated Magna Cum Laude with 3.8 GPA",
      "Dean's List all semesters",
      "President of Computer Science Club"
    ]
  }
]

