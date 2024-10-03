<div hidden>
```
@startuml
top to bottom direction
package "PresentationLayer" {
	class Service {
	    +handle_request()
	    +send_response()
	    +error_handling()
	}

	class ApiEndpoint {
	    +register_user()
	    +update_user_profile()
	    +delete_user()
	    +update_place()
	    +delete_place()
	    +list_places()
	    +add_review()
	    +list_reviews_by_place()
	    +update_amenity()
	    +list_amenities()
	}
}

class Facade {
	    +register_user()
	    +update_user_profile()
	    +delete_user()
	    +update_place()
	    +delete_place()
	    +list_places()
	    +add_review()
	    +list_reviews_by_place()
	    +update_amenity()
	    +list_amenities()
	
}

package "BusinessLogicLayer" {
	class User {
		+User()
		+is_admin()
		+register_user()
		+update_user_profile()
		+delete_user()
	}
	class Place {
		+Place()
		+update_place()
		+delete_place()
		+list_place()
	}
	class Review {
		+Review()
		+update_review()
		+delete_review()
		+list_review_by_place()
	}
	class Amenity {
		+Amenity()
		+update_amenity()
		+delete_amenity()
		+list_amenities()
	}
}

package "PersistenceLayer" {
	class UserRepository {
	    +save_user()
	    +find_user_by_id()
	    +delete_user()
	    +update_user()
	}
	    
	class PlaceRepository {
	    +save_place()
	    +find_place_by_id()
	    +delete_place()
	    +update_place()
	    +list_places()
	}
	class ReviewRepository {
	    +save_review()
	    +find_review_by_place_id()
	    +delete_review()
	    +update_review()
	    +list_reviews_by_place()
}

	class AmenityRepository {
	    +save_amenity()
	    +find_amenity_by_id()
	    +delete_amenity()
	    +update_amenity()
	    +list_amenities()
}

}

PresentationLayer ..> Facade: <<access>>
Facade ..> BusinessLogicLayer: <<access>>
BusinessLogicLayer ....> PersistenceLayer

note right of PresentationLayer
	Presentation Layer:
	- Handles interactions with users or external systems.
	- Communicates with the API to handle requests and send responses.
end note 

note right of Facade
	Facade Pattern:
	- Simplifies communication between layers. 
	- Provides a unified interface to access the Business Logic Layer.
	- Hides the complexity of the underlying system.
end note 

note right of BusinessLogicLayer
	Business Logic Layer: 
	- Contains core business rules and logic.
	- Handles operations for entities like User, Place, Review, and Amenity.
	- Manages how data is processed and transformed. 
end note 

note right of PersistenceLayer
	Persistence Layer: 
	- Handles data storage and retrieval. 
	- Interacts with the database through repositories for entities like User, Place, Review, and Amenity. 
end note

@enduml
```
</div>

![](firstDiagram.svg)
