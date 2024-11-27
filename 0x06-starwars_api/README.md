# Star Wars API :film_strip::clapper:; The ALX Project
-------------
This script fetches and prints the names of characters from a specific 
__Star Wars movie__ using the __Star Wars API__. 
The movie ID is provided as a command-line argument.

![AbramsBooks image](https://www.abramsbooks.com/cover_images/6/9781419767876_s3.jpg)

# Project Requirements :computer::heavy_check_mark: 

- All files will be interpreted on `Ubuntu 20.04 LTS` using node (`version 10.14.x`)
- All files should end with a new line
- The first line of all files should be exactly `#!/usr/bin/node`
- The code should be semistandard compliant. Rules of Standard + semicolons on top. 
- All files must be executable
- __The following prerequisites must be installed: Node.js version 10, 
a JavaScript runtime environment, and some related modules, for instance:__

__1. To install `Node.js version 10` use:__

```
$ curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
$ sudo apt-get install -y nodejs

```

__2. To install `semi-standard` use:__

```
$ sudo npm install semistandard --global

```

__3. To install `request module` use:__

```
$ sudo npm install request --global
$ export NODE_PATH=/usr/lib/node_modules

```

__To run the script, use the following command:__

```
./star-wars-api.js [movieID]

```

Replace [`movieID`] with the desired __Star Wars movie ID 3 = “Return of the Jedi”__. For instance:

```
./star-wars-api.js 3

```

This will display the characters from the __Star Wars movie ID 3 = “Return of the Jedi”__.

## How It Works :dart:

- The script takes a movie ID as a command-line argument.
- It makes a `GET` request to the __Star Wars API's /films/__ 
endpoint to fetch movie details based on the provided movie ID.
- For each character in the movie, it fetches the character's details 
using the character's URL obtained from the movie data.
- Finally, it prints the name of each character.

__Dependencies Used__:

- `request module`: This script uses the request module to make __HTTP requests__. 
The module is utilized for fetching movie and character data from the __Star Wars API__.

__Code Structure__:

- `requestCharacters() Function`: This asynchronous function fetches the list of character URLs from the specified __Star Wars movie__.
- `requestNames() Function`: This asynchronous function fetches the names of characters 
using their respective URLs obtained from the requestCharacters() function.
- `getCharNames() Function`: This main function orchestrates the entire process. 
It calls requestCharacters() to fetch character URLs, then calls requestNames() 
to fetch character names, and finally prints the names of characters to the console.

__Example Output :movie_camera::dart:__

```
Luke Skywalker
C-3PO
R2-D2
Darth Vader
Leia Organa
Obi-Wan Kenobi
Chewbacca
Han Solo
Jabba Desilijic Tiure
Wedge Antilles
Yoda
Palpatine
Boba Fett
Lando Calrissian
Ackbar
Mon Mothma
Arvel Crynyd
Wicket Systri Warrick
Nien Nunb
Bib Fortuna

```

> All comments, feedbacks and suggestions are highly welcome. Kindly take a look at my
codes to get an insight. Scroll up :arrow_up:, please.

##  Author :black_nib:
*  __Oyindamola Ibis__ <[HBIbidunni](https://github.com/HBIbidunni)>
-------
