DIAGRAM 1 (ERD)
```mermaid
erDiagram
    BOEK {
        int boek_id
        string titel
        string isbn
        int publicatiejaar
    }

    AUTEUR {
        int auteur_id
        string naam
    }

    UITGEVER {
        int uitgever_id
        string naam
    }

    LID {
        int lid_id
        string naam
        string email
    }

    UITLENING {
        int uitlening_id
        date uitleendatum
        date inleverdatum
    }

    BOEK }o--o{ AUTEUR : "geschreven door"
    UITGEVER ||--o{ BOEK : "geeft uit"
    BOEK ||--o{ UITLENING : "wordt uitgeleend"
    LID ||--o{ UITLENING : "leent"
```

DIAGRAM 2 (Sequence)
```mermaid
sequenceDiagram
    participant Gebruiker
    participant Frontend
    participant API
    participant Database

    Gebruiker->>Frontend: Klikt "Leen boek"
    Frontend->>API: POST /loans (boek_id, lid_id)
    API->>Database: Controleer beschikbaarheid boek
    Database-->>API: Boek beschikbaar
    API->>Database: Maak uitlening aan
    Database-->>API: Uitlening opgeslagen
    API-->>Frontend: 201 Created (uitlening)
    Frontend-->>Gebruiker: Bevestiging getoond
```

DIAGRAM 3 (USECASE)
```mermaid
usecaseDiagram
    actor Lid
    actor Bibliothecaris
    actor Beheerder

    Lid --> (Zoeken naar boeken)
    Lid --> (Boek lenen)
    Lid --> (Boek inleveren)
    Lid --> (Reservering maken)
    Lid --> (Account bekijken)

    Bibliothecaris --> (Boek registreren)
    Bibliothecaris --> (Uitlening beheren)
    Bibliothecaris --> (Inlevering verwerken)
    Bibliothecaris --> (Leden beheren)

    Beheerder --> (Gebruikers beheren)
    Beheerder --> (Systeeminstellingen aanpassen)
```

