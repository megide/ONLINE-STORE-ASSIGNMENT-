

Setup
Clone the repository or create a new Laravel project.

Configure the database connection by updating the .env file with your MySQL database credentials.

Run the database migration to create the necessary "categories" table:
php artisan migrate
Seed the database with sample categories for testing purposes (optional):
php artisan db:seed --class=CategorySeeder
API Endpoints
Retrieves all categories in XML format.

Endpoint: GET /categories
Response Format: XML
Response Body:
<?xml version="1.0" encoding="UTF-8"?>
<document>
    <category>
        <id>1</id>
        <name>construction</name>
        <_lft>1</_lft>
        <_rgt>2</_rgt>
        <parent_id></parent_id>
        <created_at>2023-06-08T22:18:44.000000Z</created_at>
        <updated_at>2023-06-08T22:18:44.000000Z</updated_at>
        <children/>
    </category>
    <category>
        <id>2</id>
        <name>agriculture</name>
        <_lft>3</_lft>
        <_rgt>4</_rgt>
        <parent_id></parent_id>
        <created_at>2023-06-08T22:18:44.000000Z</created_at>
        <updated_at>2023-06-08T22:18:44.000000Z</updated_at>
        <children/>
    </category>
    <category>
        <id>3</id>
        <name>fashion</name>
        <_lft>5</_lft>
        <_rgt>6</_rgt>
        <parent_id></parent_id>
        <created_at>2023-06-08T22:18:44.000000Z</created_at>
        <updated_at>2023-06-08T22:18:44.000000Z</updated_at>
        <children/>
    </category>
    
</document>
Retrieve a Specific Category
Retrieves a specific category by its ID in XML format.

Endpoint: GET /categories/{id}
Response Format: XML
Response Body:
<category>
        <id>1</id>
        <name>ELECTRONIC</name>
        <_lft>1</_lft>
        <_rgt>2</_rgt>
        <parent_id></parent_id>
        <created_at>2023-06-08T22:18:44.000000Z</created_at>
        <updated_at>2023-06-08T22:18:44.000000Z</updated_at>
        <children/>
    </category>
Create a New Category
Creates a new category.

Endpoint: POST /categories
Request Format: XML
Request Body:
<category>
  <name>New Category</name>
  <parent_id>1</parent_id>
</category>
Response Format: XML
Response Body:
<category>
  <id>3</id>
  <name>New Category</name>
  <lft>4</lft>
  <rgt>5</rgt>
  <created_at>2023-06-03 12:00:00</created_at>
  <updated_at>2023-06-03 12:00:00</updated_at>
</category>
Update an Existing Category
Updates an existing category by its ID.

Endpoint: PUT /categories/{id}
Request Format: XML
Request Body:
<category>
        <id>1</id>
        <name>ELECTRONIC_devices</name>
        <_lft>1</_lft>
        <_rgt>2</_rgt>
        <parent_id></parent_id>
        <created_at>2023-06-08T22:18:44.000000Z</created_at>
        <updated_at>2023-06-08T22:40:44.000000Z</updated_at>
        <children/>
    </category>
Response Format: XML
Response Body:
<category>
  <id>3</id>
  <name>Updated Category</name>
  <lft>4</lft>
  <rgt>5</rgt>
  <created_at>2023-06-03 12:00:00</created_at>
  <updated_at>2023-06-04 12:00:00</updated_at>
</category>
Delete a Category
Deletes a category by its ID.

Endpoint: DELETE /categories/{id}
Response Format: XML
Response Body:
<message>Category deleted successfully.</message>
Error Handling
The API handles errors and returns appropriate error responses in XML format. For example, if a requested category is not found, the API will respond with:
<error>Category not found.</error>
Unit Tests
Unit tests have been implemented to ensure the functionality of the API endpoints. Run the following command to execute the tests:
php artisan test
