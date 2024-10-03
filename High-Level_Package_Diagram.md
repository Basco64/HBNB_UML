```mermaid
classDiagram

class PresentationLayer {
    <<Interface>>
    +servieAPI()
    +HandleUserRequest()
}
class BusinessLogicLayer {
    -User
    -Place
    -Review
    -Amenity
    -Process()
}
class PersistenceLayer {
    -DatabaseStorage
    -CRUD()
}

PresentationLayer --> BusinessLogicLayer : Facade Pattern
BusinessLogicLayer --> PersistenceLayer : DataBase Operations
```
