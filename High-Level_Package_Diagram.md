``` mermaid

classDiagram

class PresentationLayer {
    class UI
    interface FacadeServiceAPI
}
class BusinessLogicLayer {
     <<ModelClasses>> 
        class User
        class Place
        class Review
        class Amenity
    
}
class PersistenceLayer {
     class DatabaseAccess
}

UI --> FacadeServiceAPI : Sends Data

PresentationLayer ..> BusinessLogicLayer : Facade Pattern

BusinessLogicLayer ..> PersistenceLayer : Database Operations
```
