---
title: D'Amico Recipe API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell


toc_footers:
  - <a href='https://github.com/miamiyankee13/damico-recipes-api'>View D'Amico Recipes API on GitHub</a>
  - <a href='https://github.com/miamiyankee13/damico-recipes-client'>View D'Amico Recipes Client on GitHub</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the D'Amico Reecipes API! You can use our API to access D'Amico Recipes API endpoints, which can interact with our database of recipes, as well as the D'Amico Recipes client application.

# Recipes

## Get All Recipes

> To retrieve all recipes, use this code:

```shell
curl -X GET 
  https://damico-recipes-api.herokuapp.com/api/recipes
```

> The above command returns a 200 status code and a JSON object containing an array of all existing recipes like this:

```json
{
  "recipes": [
    {
      "_id": "5cb0fca6801931051237cdf0",
      "name": "Baked Chicken Cutlets",
      "ingredients": [
          "Chicken Breast",
          "Egg (1)",
          "Bread Crumbs",
          "Grated Cheese"
      ],
      "instructions": [
          "Cut chicken breast into thin cutlets",
          "Sramble egg in bowl",
          "Dip cutlets in bowl",
          "Coat egg-dipped cutlets in bread crumbs",
          "Bake in oven at 350 for 20 mins, flipping halfway through",
          "Top with grated cheese & serve with side of choice"
      ],
      "sides": [
          "Vegetable Pasta",
          "Broccoli",
          "Asparagus",
          "Zucchini",
          "Spinach"
      ],
      "meal": "dinner",
      "type": "chicken"
    },
    {
      "_id": "5ceac2cc9bac1c0017ac7386",
      "name": "Banana Pancakes",
      "ingredients": [
          "Banana (1)",
          "Egg (1)"
      ],
      "instructions": [
          "Mash banana in bowl",
          "Add egg",
          "Scramble mixture",
          "Pour into pan as 3 separate pancakes",
          "Cook over medium flame until edges are golden brown",
          "Serve with side of choice"
      ],
      "sides": [
          "Peanut Butter",
          "Turkey Bacon"
      ],
      "meal": "breakfast",
      "type": "pancakes"
    },
    ...more recipes
  ]
}
```

This endpoint retrieves all existing recipes from the database.

### HTTP Request

`GET https://damico-recipes-api.herokuapp.com/api/recipes`


## Get an Individual Recipe

> To retrieve an individual recipe, use this code:

```shell
curl -X GET
  https://damico-recipes-api.herokuapp.com/api/recipes<id>
```

> The above command returns a 200 status code and a JSON object containing specific recipe information like this:

```json
{
  "_id": "5cb0fca6801931051237cdf0",
  "name": "Baked Chicken Cutlets",
  "ingredients": [
      "Chicken Breast",
      "Egg (1)",
      "Bread Crumbs",
      "Grated Cheese"
  ],
  "instructions": [
      "Cut chicken breast into thin cutlets",
      "Sramble egg in bowl",
      "Dip cutlets in bowl",
      "Coat egg-dipped cutlets in bread crumbs",
      "Bake in oven at 350 for 20 mins, flipping halfway through",
      "Top with grated cheese & serve with side of choice"
  ],
  "sides": [
      "Vegetable Pasta",
      "Broccoli",
      "Asparagus",
      "Zucchini",
      "Spinach"
  ],
  "meal": "dinner",
  "type": "chicken"
}
```

This endpoint retrieves an individual recipe from the database.

### HTTP Request

`GET https://damico-recipes-api.herokuapp.com/api/recipes/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | id of the recipe to retrieve


## Get Recipes by Meal

> To retrieve recipes by meal, use this code:

```shell
curl -X GET 
  https://damico-recipes-api.herokuapp.com/api/recipes/<meal>
```

> The above command returns a 200 status code and a JSON object containing an array of all existing recipes matching the specified meal like this:

```json
{
  "recipes": [
    {
      "_id": "5ceac2cc9bac1c0017ac7386",
      "name": "Banana Pancakes",
      "ingredients": [
          "Banana (1)",
          "Egg (1)"
      ],
      "instructions": [
          "Mash banana in bowl",
          "Add egg",
          "Scramble mixture",
          "Pour into pan as 3 separate pancakes",
          "Cook over medium flame until edges are golden brown",
          "Serve with side of choice"
      ],
      "sides": [
          "Peanut Butter",
          "Turkey Bacon"
      ],
      "meal": "breakfast",
      "type": "pancakes"
    },
    ...more recipes with same meal property value
  ]
}
```

This endpoint retrieves all existing recipes matching the specified meal from the database.

### HTTP Request

`GET https://damico-recipes-api.herokuapp.com/api/recipes/<meal>`

### URL Parameters

Parameter | Description
--------- | -----------
meal | meal of the recipes to retrieve

## Get Recipes by Type

> To retrieve recipes by type, use this code:

```shell
curl -X GET 
  https://damico-recipes-api.herokuapp.com/api/recipes/<type>
```

> The above command returns a 200 status code and a JSON object containing an array of all existing recipes matching the specified type like this:

```json
{
  "recipes": [
    {
      "_id": "5ceac2cc9bac1c0017ac7386",
      "name": "Banana Pancakes",
      "ingredients": [
          "Banana (1)",
          "Egg (1)"
      ],
      "instructions": [
          "Mash banana in bowl",
          "Add egg",
          "Scramble mixture",
          "Pour into pan as 3 separate pancakes",
          "Cook over medium flame until edges are golden brown",
          "Serve with side of choice"
      ],
      "sides": [
          "Peanut Butter",
          "Turkey Bacon"
      ],
      "meal": "breakfast",
      "type": "pancakes"
    },
    ...more recipes with same type property value
  ]
}
```

This endpoint retrieves all existing recipes matching the specified type from the database.

### HTTP Request

`GET https://damico-recipes-api.herokuapp.com/api/recipes/<type>`

### URL Parameters

Parameter | Description
--------- | -----------
type | type of the recipes to retrieve


## Create a Recipe

> To create a recipe, use this code:

```shell
curl -X POST
  https://damico-recipes-api.herokuapp.com/api/recipes
  -H 'Content-Type: application/json'
  -d '{
	"name": "Baked Chicken Cutlets",
    "ingredients": [
        "Chicken Breast",
        "Egg (1)",
        "Bread Crumbs",
        "Grated Cheese"
    ],
    "instructions": [
        "Cut chicken breast into thin cutlets",
        "Sramble egg in bowl",
        "Dip cutlets in bowl",
        "Coat egg-dipped cutlets in bread crumbs",
        "Bake in oven at 350 for 20 mins, flipping halfway through",
        "Top with grated cheese & serve with side of choice"
    ],
    "sides": [
        "Vegetable Pasta",
        "Broccoli",
        "Asparagus",
        "Zucchini",
        "Spinach"
    ],
    "meal": "dinner",
    "type": "chicken"
}'
```

> The above command returns a 201 status code and a JSON object containing the recipe information like this:

```json
{
    "_id": "5cb0fca6801931051237cdf0",
    "name": "Baked Chicken Cutlets",
    "ingredients": [
        "Chicken Breast",
        "Egg (1)",
        "Bread Crumbs",
        "Grated Cheese"
    ],
    "instructions": [
        "Cut chicken breast into thin cutlets",
        "Sramble egg in bowl",
        "Dip cutlets in bowl",
        "Coat egg-dipped cutlets in bread crumbs",
        "Bake in oven at 350 for 20 mins, flipping halfway through",
        "Top with grated cheese & serve with side of choice"
    ],
    "sides": [
        "Vegetable Pasta",
        "Broccoli",
        "Asparagus",
        "Zucchini",
        "Spinach"
    ],
    "meal": "dinner",
    "type": "chicken"
}
```

This endpoint creates a new recipe, adding it to the database.

### HTTP Request

`POST https://damico-recipes-api.herokuapp.com/api/recipes`

### Required Fields
Field | Description
----- | -----------
name | recipe name
ingredients | recipe ingredients
instructions | recipe instructions
sides | recipe sides
meal | recipe meal
type | recipe type

## Edit a Recipe

> To edit a recipe, use this code:

```shell
curl -X PUT
  https://damico-recipes-api.herokuapp.com/api/recipes/<id>
  -H 'Content-Type: application/json'
  -d '{
	"_id": "5cb0fca6801931051237cdf0",
    "name": "Fried Chicken Cutlets",
    "ingredients": [
        "Chicken Breast",
        "Egg (1)",
        "Bread Crumbs",
        "Grated Cheese"
    ],
    "instructions": [
        "Cut chicken breast into thin cutlets",
        "Sramble egg in bowl",
        "Dip cutlets in bowl",
        "Coat egg-dipped cutlets in bread crumbs",
        "Cook in oil over medium flame",
        "Top with grated cheese & serve with side of choice"
    ],
    "sides": [
        "Vegetable Pasta",
        "Broccoli",
        "Asparagus",
        "Zucchini",
        "Spinach"
    ],
    "meal": "dinner",
    "type": "chicken"
}'
```

> The above command returns a 200 status code and a JSON object containing the updated data like this:

```json
{
  "_id": "5cb0fca6801931051237cdf0",
  "name": "Fried Chicken Cutlets",
  "ingredients": [
      "Chicken Breast",
      "Egg (1)",
      "Bread Crumbs",
      "Grated Cheese"
  ],
  "instructions": [
      "Cut chicken breast into thin cutlets",
      "Sramble egg in bowl",
      "Dip cutlets in bowl",
      "Coat egg-dipped cutlets in bread crumbs",
      "Cook in oil over medium flame",
      "Top with grated cheese & serve with side of choice"
  ],
  "sides": [
      "Vegetable Pasta",
      "Broccoli",
      "Asparagus",
      "Zucchini",
      "Spinach"
  ],
  "meal": "dinner",
  "type": "chicken"
}
```

This endpoint edits an exisintg recipe in the database.

### HTTP Request

`PUT https://damico-recipes-api.herokuapp.com/api/recipes/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | id of the recipe to edit

### Required Fields
Field | Description
----- | -----------
_id | id of the recipe to edit

### Optional Fields
Field | Description
----- | -----------
name | recipe name
ingredients | recipe ingredients
instructions | recipe instructions
sides | recipe sides
meal | recipe meal
type | recipe type


## Delete a Recipe

> To delete a recipe, use this code:

```shell
curl -X DELETE
  https://damico-recipes-api.herokuapp.com/api/recipes/<id>
```

> The above command returns a 204 status code.

This endpoint deletes an existing recipe from the database.

### HTTP Request

`DELETE https://damico-recipes-api.herokuapp.com/api/recipes/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | id of the recipe to delete