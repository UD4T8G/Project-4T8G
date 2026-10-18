# Project 4T8G -- Universe Architecture Framework

```text
4 Taegeuk 8 Gua
  ☯ -- Cross
  ☰ -- Trinity
  ☱ -- Ichthus
  ☲ -- Fire
  ☳ -- Swastika
  ☴ -- Typhoon
  ☵ -- Water
  ☶ -- Bolt
  ☷ -- Hexagram
```

> *A Software Engineering Framework & Structural Schema for Worldbuilding Maintenance.*

---

## overview-&-design-philosophy

* **Project 4T8G** is an architectural framework designed to eliminate lore contradictions, setting conflicts, and maintenance bottlenecks in complex fictional universes by applying software engineering methodologies.
* To guarantee data integrity and long-term maintainability, any universe built upon this framework strictly adheres to three foundational structural constraints:

1. **Minimizing Control Flow Complexity**  
Eliminates tangled exception handling by modeling all status effects, power sources, and resource exchanges into simplified directed graphs.
2. **Strict Encapsulation**  
Logically hides the internal computation logic of individual entities (power sources, conditional triggers, state transformations). External modules cannot arbitrarily manipulate internal states, protecting core lore integrity.
3. **Separation of Concerns (SoC)**  
Strictly decouples the global system rule layer from individual object definitions, fundamentally preventing systemic side effects caused by local lore edits.

---

## the-tripartite-file-standard

* Every domain or entity within this framework is structured into a standardized **Tripartite File Set (`Header`, `Main`, `Source`)**, enforcing clear boundary lines between mechanics, narrative execution, and reference data:

```text
       ┌────────────────────────────────────────────────────────┐
       │                   Tripartite File Set                  │
       ├───────────────────┬──────────────────┬─────────────────┤
       │     *_Header      │      *_Main      │     *_Source    │
       │ (Logic & Specs)   │ (Execution & Flow)│ (Verification) │
       └─────────┬─────────┴────────┬─────────┴────────┬────────┘
                 │                  │                  │
                 ▼                  ▼                  ▼
          System Mechanics    Sequence & Lines   Academic Roots
```

| File Standard | Layer | Responsibility & Scope |
| :--- | :--- | :--- |
| **`*_Header.md`** | **Logic & Mechanics** | Structural constraints, parameters, equipment modules, department rules, state transition graphs. |
| **`*_Main.md`** | **Execution & Narrative** | Timeline sequences (Prequel, Spin-off, Sequel), character traits, and dialogue scripts. |
| **`*_Source.md`** | **Verification & Reference** | Philological/Academic references, raw concepts, design footnotes, and textual criticism sources. |

---

## template-directory-structure

* The open-source core framework provides boilerplate templates located under the `template/` directory

```text
template/
├── core/
|   └── core-template/
│      ├── Core-Template_Header.md        # Boilerplate for global rules & department specs
│      ├── Core-Template_Main.md          # Boilerplate for main storyline & timeline sequences
│      └── Core-Template_Source.md        # Boilerplate for system-wide references & concepts
│
└── characters/
    └── characters-template/
        ├── Characters-Template_Header.md # Boilerplate for entity parameters & encapsulation
        ├── Characters-Template_Main.md   # Boilerplate for entity characteristics & lines
        └── Characters-Template_Source.md # Boilerplate for entity-specific design references
```

---

## getting-started

1. **Copy Templates**  
Copy the contents of `template/` into your active worldbuilding workspace.
2. **Define Core Rules**  
Fill out [Core-Template_Header.md](./template/core/core-template/Core-Template_Header.md) to establish global constraints before creating entities.
3. **Encapsulate Entities**  
Define independent character parameters inside [Characters-Template_Header.md](./template/characters/characters-template/Characters-Template_Header.md), ensuring internal state computations remain private to the entity.
4. **Link Narrative Sequences**  
Reference defined headers inside `Main` files using structured Markdown relative links.

---

## license

* **Framework Templates (`template/` directory)**
  - Licensed under the open-source **[MIT License](./LICENSE.md)**. Anyone is free to use, adapt, and distribute these architectural schemas for their own worldbuilding projects.
  - The [MIT License](./LICENSE.md) applies ONLY to `template/`. All other directories (`docs/`, `reference_arts/`, etc.) remain strictly ALL RIGHTS RESERVED.