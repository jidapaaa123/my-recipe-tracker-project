# my-recipe-tracker-project
ASP.NET Core Web API & Postgres DB in Docker Re-do and Revamp of Recipe Tracker from Intro to Web Dev  
  
# Purpose  
- TDD  
- API  
- MAUI, Blazor  
- Postgres, EF Core  
- Account support (I'll make my database ready to store encrypted passwords & stuff, but I think I'll leave that for when I'm more confident in security)  
- I personally don't enjoy doing UI, but I'll also get to do that here because it's a one-woman army  
- Docker, Kubernetes and other mystical things I'm learning in Operations this semester...  

# Features?  
- recipe tracker (same features from old one)
- nutrition tracking  
- experimenting tab: different recipes for the SAME "dish." To aid experimentation with recipes until the user decides to confirm on 1. Ease of photos & captions to help with the experimentation process.  

# SUMMARY  
- Experimental Recipes --> Pending Recipes --> Recipe Collection
- External API Recipe --> Pending Recipes
- Nutrition (optional per recipe-- but if they track 1 ingredient, they must track all, type of thing): user can name their ingredient whatever (hopefully they don't link peach to cream cheese, but hey), and will "link" to a food provided by the Nutrition API that they feel represents it the best. Logic must support conversions here  
- Smart Recipe search (as smart as I can. oooh this is so scalable): like the old one, the heart of this app is to recognize when you don't mind substituting ingredients or missing optional ingredients.  

# External API's & Other Tools  
- Edamam, for importing recipes : https://www.edamam.com/  
- FatSecret, for nutrition info: https://platform.fatsecret.com/  
- Humanizr (package), for recognizing egg == eggs: https://github.com/Humanizr/Humanizer  
- UnitsNet (package), for unit conversion: https://github.com/angularsen/UnitsNet  

OLD PORT (that I'm still keeping):  
Page 1: Pantry - Ingredients list: Here will be rendered cards of all ingredients the user has entered. The purpose is not what they currently have per se, but more so common ingredients they may refer to often. They will then be able to drag-and-drop those ingredients into the basket (or cart?). Those things in the basket actually represent what they do currently have. The point is to avoid having to re-type "eggs", "milk", "chicken", "paprika", "water" over and over, as they are common ingredients most households have almost all the time. The user may continue to remove things out of the basket via also drag-n-drop. User may delete a pantry ingredient. I'm also thinking of a feature where new ingredients introduced in recipes automatically show up in the pantry, but this is tentative.

Page 2: Pending Recipes: Recipes in draft. The user may create an instance of an empty "recipe" then edit it as they wish. They will only be able to mark it complete once all the required fields are entered. Once marked complete, the pending recipe will be "sent" to Recipes Collection (Page 3). Some uses for this page may include writing down a name of a dish the user has just heard about but has no other information about it. Another use may be writing up a nameless recipe, or testing out a new recipe in writing. This is the only page where they can edit a recipe, and the first place any recipe goes to. I'm thinking of referring to an external API for pre-made recipes, but I haven't found a good one yet. Once I do, those "imported recipes" will still show up here. I might add another page for importing recipes, where the user selects which ones they want to take to this Pending Recipes page. Editing a draft will bring them to the full page of the recipe. When making the ingredients list, each ingredient will have a drop-down for whether it's optional. For substitutes, there will render a place to enter each substitute item (max 3 per ingredient). The user may reset their inputs in the ingredient adder.

Page 3: Recipes Collection: This is where the search algorithm searches for recipes based on user input (by ingredient OR by name). It will filter by ingredients the user has in their basket, and whether they allow substitutes and recipes whose optional ingredients are missing from the basket. The recipe cards' recipe titles will be a link to the full page of the recipe, which will be formatted similar to recipe websites we can already find online (but way, way simpler and without a 3-page backstory), and uses query strings to render the appropriate recipe. Substitutes will be listed as (Substitutes: item1 / item 2 / item 3...). The side panel of the Recipes Collection page will also be a sliding side panel to see what you've got currently in your basket. The user can press "Cook!" on a recipe to note that they made it (this is so I can incorporate a table in somehow)

Page 4: Import Recipes from an external API. Will render recipe cards based on user search, then the user may pick which ones to send to Pending Recipes (where they can make it their own)

Page 5: Home explanation for each page  

