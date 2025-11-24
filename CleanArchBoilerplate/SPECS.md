# SPECS – CleanArchBoilerplate

## Funktionalitet
Detta projekt är ett Clean Architecture boilerplate för .NET.  
Syftet är att ge en färdig, återanvändbar grundstruktur för nya backend-projekt.

## Features
- En enkel domänentitet: `ExampleEntity`
- Use cases i Application-lagret:
  - `CreateExample`
  - `GetAllExamples`
- Generic Repository pattern med `IGenericRepository<T>`
- Infrastruktur med EF Core (inmemory i detta boilerplate)
- API-lager med controllers och dependency injection

## API Endpoints
### GET `/api/example`
Hämtar alla Example-objekt via Application-lagrets use case.

### POST `/api/example`
Skapar ett nytt Example-objekt via Application-lagrets use case.

## Regler och begränsningar
- API får inte prata direkt med databasen.
- All logik går genom:
  API → Application → Domain → Infrastructure
- Domain-lagret innehåller ingen extern beroende-kod.
