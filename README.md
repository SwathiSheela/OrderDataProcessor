# OrderDataProcessor
OrderDataProcessor Project - Code Structure & Standards
This document outlines the code structure and design principles followed in the OrderProcessor
project.
1. Separation of Concerns (SoC)
-------------------------------
Each responsibility is encapsulated in a dedicated class:
- FileParserService.cs: Reads and parses the CSV file.
- DestinationResolverService.cs: Resolves destination based on supplier code or name.
- XmlGeneratorService.cs: Converts the parsed data into XML format.
- Program.cs: Main entry point, orchestrates parsing, transformation, and output.
2. Readability and Simplicity (KISS)
------------------------------------
- The logic is broken down into clear, understandable methods.
- Business rules (like default destinations) are centralized.
- Complexity is minimized through modular functions and early returns.
3. Don't Repeat Yourself (DRY)
------------------------------
- Shared logic and data models are extracted into reusable components (Models, Utilities).
- Avoided code duplication in data transformation and validation.
4. SOLID Principles
-------------------
- Single Responsibility: Each class has one clearly defined role.
- Open/Closed: Logic is extensible (e.g., adding new destination rules).
- Liskov Substitution: Classes are structured in a way to allow future interface abstraction.
- Interface Segregation: Project is structured for easy interface extraction if scaling.
- Dependency Inversion: Classes can be refactored to support DI for testability.
5. Models and Data Flow
------------------------
- HeaderRecord.cs and DetailRecord.cs represent structured data parsed from CSV.
- FileParserService groups headers and details appropriately.
- XmlGeneratorService serializes data into the required XML format with proper structure.
6. Extensibility and Testability
--------------------------------
- Code is structured to support unit testing (mockable classes, stateless methods).
- Clean structure allows easy modifications for additional input/output formats.
This structure ensures the solution is easy to maintain, extend, and test while following best
practices.
