# Smart Home Simulator - Testy

### Autor: Jakub Jurkian

### Grupa: 2

## Opis projektu

Projekt Smart Home Simulator to kompleksowy system zarządzania inteligentnym domem z interfejsem webowym.
Obejmuje backend w .NET, frontend w React/TypeScript oraz komunikację MQTT.
System posiada logikę użytkownika oraz umożliwia zarządzanie urządzeniami, pomieszczeniami i logami konserwacji.

## Uruchomienie testów

### Testy jednostkowe

```bash
dotnet test tests/SmartHome.UnitTests/SmartHome.UnitTests.csproj
```

### Testy integracyjne

```bash
dotnet test tests/SmartHome.IntegrationTests/SmartHome.IntegrationTests.csproj
```

### Testy BDD (Reqnroll)

```bash
dotnet test tests/SmartHome.BDDTests/SmartHome.BDDTests.csproj
```

### Testy wydajnościowe

```bash
dotnet test tests/SmartHome.PerformanceTests/SmartHome.PerformanceTests.csproj
```

### Wszystkie testy

```bash
dotnet test
```

### Test coverage

```bash
dotnet test --collect:"XPlat Code Coverage"

reportgenerator -reports:"**/coverage.cobertura.xml" -targetdir:"coveragereport" -reporttypes:Html -classfilters:"-SmartHome.Api.BackgroundServices.TcpSmartHomeServer;-SmartHome.Infrastructure.Migrations.*"
```

## Pipeline CI/CD

Pipeline GitHub Actions uruchamia się automatycznie przy każdym push i pull request do gałęzi main.

### Ręczne uruchomienie pipeline

Przejdź do zakładki Actions w repozytorium GitHub
Wybierz workflow ".NET CI"
Kliknij Run workflow

### Lokalne uruchomienie z Docker Compose

```bash
docker-compose up -d
```

## Raport pokrycia kodu

Po uruchomieniu testów raport pokrycia znajduje się w katalogu coveragereport/index.html.
