# Project Vue-Pokemon


 ### Task Description

Develop a small single page web application using Vue JS that lists Pokemon characteristics. Use the
attached layout design and pictures provided as a base. (Layout designs are just examples).

In order to accomplish this task you'll have to use the https://pokeapi.co/ APIs to get the necessary
information. Here is a link to the documentation:

https://pokeapi.co/docs/v2.html#pokemon

The items in this list are increasing in complexity, try to do as much as you can, but it is not
mandatory to do all of them. Read all items before starting, so as to have a proper planning of your
development.

1. Create a single page web app that lists the abilities of 3 Pokemon (Pikachu, Ditto and
Charmander). You should be able to click the image of a Pokemon and see that Pokemon's
name and abilities.

2. List the Moves of this Pokemon in another column, only list the names of the moves.

3. List the Stats of this Pokemon in another column, list the name of each stat and the
'base_stat' value.

4. Lazy load the information (only make API calls when necessary, and save the information),
and have loading states while making the calls.

5. Instead of choosing between 3 Pokemon's, use a search bar to search any Pokemon by name
(there is a second layout design you can use for this, Use this API to get the Pokemon list:

apiUrl : "https://pokeapi.co/api/v2/pokemon/".

imgUrl : "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/".

6. Search should be done by clicking a 'search' button or by pressing 'Enter' key, button and key
should be disabled if input is empty.

7. Display the image of the Pokemon using the sprites.front_layout property of the response
from the API call.


Requirements:

● Should default to the Pikachu on initial load.
● Design should be responsive.
● Proper error handling (Fx: If search is unsuccessful, then show message to the user).
Zip all files and rename any .js files to a .txt extension in order to bypass email client restrictions.


### Install npm
```
npm install
```

### Run Vue

```
 run dev s
```