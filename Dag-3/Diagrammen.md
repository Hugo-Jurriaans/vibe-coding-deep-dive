Roadmap Diagram:

```mermaid
flowchart LR
    %% User Input
    UI[Player Input (Mouse / Touch)] --> INPUT[Input Handler]

    %% Game State
    INPUT --> STATE[Game State Manager]
    STATE --> LOOP[Game Loop]

    %% Core Systems
    LOOP --> FISHING[Fishing System]
    LOOP --> UIRENDER[UI Renderer]
    LOOP --> WORLD[World System]

    %% Fishing Flow
    FISHING --> CAST[Casting Logic]
    CAST --> BOBBER[Bobber Position]
    BOBBER --> BITE[Fish Bite Timer]
    BITE --> REEL[Reel Mini-Game]
    REEL --> RESULT[Catch Result]

    %% Data Updates
    RESULT --> INVENTORY[Inventory and Rewards]
    INVENTORY --> PROGRESSION[Progression System]
    PROGRESSION --> JOURNAL[Fish Journal]

    %% Rendering
    WORLD --> RENDER[Canvas Renderer]
    FISHING --> RENDER
    UIRENDER --> RENDER

    %% Persistence
    PROGRESSION --> SAVE[Save System (localStorage)]
    SAVE --> LOAD[Load System]
    LOAD --> STATE

    %% Audio
    FISHING --> AUDIO[Audio System]
    UIRENDER --> AUDIO

    %% Feedback Loop
    RENDER --> LOOP
```
