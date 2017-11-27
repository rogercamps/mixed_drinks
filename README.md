# mixed_drinks

Mixed Drinks RESTful API

General
This project should involve a postgres database, an express server, and pg-promise. It is a RESTful API, and all responses should be in JSON format. If don't know any cocktails, make some up!
User Stories
As a user, I want to be able to add an ingredient to the database, using a JSON POST to the route /api/ingredients/add   Example POST data:

{ "ingredient_name": "tequila" }


As a user, I want to see this response message if an ingredient is added successfully:

{ "status": "success",
   "message": "Ingredient successfully added." }


As a user, I want to be able to see a list of all the ingredients that have been added to the database, using a GET to the route /api/ingredients/list   Example output:

[ { "ingredient_id": 1, "ingredient_name": "tequila" },
  { "ingredient_id": 2, "ingredient_name": "lime juice" },
  { "ingredient_id": 3, "ingredient_name": "triple sec" } ]


As a user, I want to be able to add a cocktail at the route /api/cocktails/add with a POST of the name and ingredients. Example POST data:

{ "cocktail_name": "margarita",
  "ingredient_ids": [ 1, 2, 3 ] }


As a user, I want to see this response message if a cocktail is added successfully:

{ "status": "success",
   "message": "Cocktail successfully added." }


As a user, I want to see a response status of 418 (look it up!) and an error if I submit a cocktail to /api/cocktails/add that includes an ingredient_id that doesn't exist in the db. I don't want the cocktail to be added to the database in this case. Example error response:

{ "status": "error",
  "message": "ingredient_id 1343 does not exist in the system. Cocktail not added." }


As a user, I want to be able to see a list of all cocktails in the db from the GET route /api/cocktails/list   Example output:

[ { "cocktail_id": 1, "cocktail_name": "margarita"},
  { "cocktail_id": 2, "cocktail_name": "screwdriver"},
  { "cocktail_id": 3, "cocktail_name": "tequila sunrise"} ]


As a user, I want to be able to see a cocktail's name and ingredient names when I access it via GET from cocktails/:id   Example output:

{ "cocktail_name": "margarita",
  "ingredient_names": [ "tequila", "lime juice", "triple sec" ] }


As a user, I want to see a response status of 404 an error if I try to access a cocktail id via cocktails/:id that doesn't exist in the database. Example error response:

{ "status": "error",
  "message": "cocktail_id 1325 does not exist in the system." }


Further Study
Make a route that returns an ingredient name and all cocktails with that ingredient, for a given ingredient id.
Make a route that returns the top five ingredients (that is, the five ingredients that are used in the most drinks).
Make a route that returns all ingredients with a list of cocktails they're included in.  Be sure to include ingredients that have no cocktails associated.
Write unit tests for your db functions.
Write integration tests for your routes.
Write a web interface using pug or ejs.
Include ingredient amounts in your cocktail recipes.
