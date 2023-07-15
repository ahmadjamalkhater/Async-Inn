
# Project: Async Inn Hotel Asset Management System

Name: ahmad khater

Date: 15/07/2023

![ERD](./Async-Inn/ERD.png)

## Explanation of Tables:

### Table1: Location

Primary Key: location_id
Columns: name, city, state, address, phone_number
Explanation: The Location table represents the different hotel locations of Async Inn. Each location has a unique ID (location_id) and stores information such as the name, city, state, address, and phone number.
### Table2: Room

Primary Key: room_id
Foreign Key: location_id
Columns: nickname, price, pet_friendly
Explanation: The Room table represents individual rooms in each hotel location. Each room has a unique ID (room_id) and is associated with a specific location through the foreign key (location_id). It also includes a nickname for better identification, the price of the room, and a flag indicating whether it is pet friendly.
### Table3: Amenity

Primary Key: amenity_id
Columns: name
Explanation: The Amenity table stores the available amenities offered by Async Inn. Each amenity has a unique ID (amenity_id) and a name describing the amenity itself, such as "air conditioning," "coffee maker," or "ocean view."
### Table4: RoomAmenity (Pure Join Table)

Foreign Keys: room_id, amenity_id
Explanation: The RoomAmenity table represents the many-to-many relationship between rooms and amenities. It contains the foreign keys room_id and amenity_id, referencing the Room and Amenity tables, respectively. This table allows multiple amenities to be associated with each room and vice versa.
### Table5: RoomLayout (Enum)

Primary Key: layout_id
Columns: name
Explanation: The RoomLayout table defines the different layouts available for hotel rooms in Async Inn. It is an enumeration table with a unique ID (layout_id) and a name describing the layout, such as "One Bedroom," "Two Bedrooms," or "Studio."
### Table6: RoomLayoutRoom (Joint Entity Table with Payload)

Foreign Keys: room_id, layout_id
Explanation: The RoomLayoutRoom table represents the relationship between rooms and room layouts. It acts as a joint entity table with payload. It contains the foreign keys room_id and layout_id, connecting the Room and RoomLayout tables, respectively. This table allows multiple room layouts to be associated with each room, enabling the hotel to have various room configurations.

### Relationships:

Location (1) - (N) Room: Each location can have multiple rooms, but each room belongs to only one location.
Room (N) - (M) Amenity: Each room can have multiple amenities, and each amenity can be associated with multiple rooms.
Room (N) - (M) RoomLayout: Each room can have multiple room layouts, and each room layout can be associated with multiple rooms.
Room (N) - (M) RoomAmenity: Each room can have multiple RoomAmenity, and each RoomAmenity can be associated with multiple rooms.
Room (N) - (M) RoomLayoutRoom:Each room can have multiple RoomLayoutRoom, and each RoomLayoutRoom can be associated with multiple rooms.
Amenity (N) - (M) RoomAmenity : Each Amenity can have multiple RoomAmenity, and each RoomAmenity can be associated with multiple Amenity.
RoomLayout (N) -(M) RoomLayoutRoom : Each RoomLayout can have multiple RoomLayoutRoom, and each RoomLayoutRoom can be associated with multiple RoomLayout.