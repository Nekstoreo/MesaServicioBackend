# MesaServicio Backend

API de Mesa de Servicio (Service Desk) construida con .NET 10, Clean Architecture y patrón de modular monolith.

## Stack

| Tecnología | Versión |
|------------|---------|
| .NET | 10 |
| PostgreSQL | 18+ |
| EF Core | 10 |
| SignalR | - |
| Auth | JWT + LDAP |
| Blob Storage | Azurite |
| SMTP | MailHog |
| Logging | Serilog |
| Testing | xUnit |

## Requisitos previos

- [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0)
- [Docker](https://docs.docker.com/get-docker/) + Docker Compose

## Quick Start

```bash
# 1. Clonar el repositorio
git clone <url-del-repo>
cd MesaServicioBackend

# 2. Levantar servicios (PostgreSQL, MailHog, Azurite)
cd docker-ad
docker-compose up -d
cd ..

# 3. Compilar
dotnet build MesaServicioSolucion.sln

# 4. Aplicar migraciones
dotnet ef database update --project MesaServicio.Infrastructure --startup-project MesaServicio.Api

# 5. Ejecutar pruebas
dotnet test MesaServicioSolucion.sln

# 6. Iniciar la API
cd MesaServicio.Api
dotnet run --launch-profile http
```

La API estará disponible en `http://localhost:5154`.
