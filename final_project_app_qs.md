# SI 364 - Final Project questions

## Overall

* **What's a one-two sentence description of what your app will do?**
A user will be able to search for a song name they know of and save it to their database. They can then either send this song to a friend or continue adding songs.

## The Data

* **What data will your app use? From where will you get it? (e.g. scraping a site? what site? -- careful not to run it too much. An API? Which API?)**
This will use either itunes or spotify

* **What data will a user need to enter into a form?**
One form will ask for a song name and return the top 5 songs. There will be a load more button if the song of choice is not there.
Another form will ask the user to enter friends' names and emails for later sending needs.

* **How many fields will your form have? What's an example of some data user might enter into it?**
The first form will have one. The second form will have 3 fields. The first will be a name, the second an email address, and the third will be a checkbox to indicate whether this person should be on your top friends list.

* **After a user enters data into the form, what happens? Does that data help a user search for more data? Does that data get saved in a database? Does that determine what already-saved data the user should see?**
In each case, data is saved immidiately. If the user has a top three friends, that will show at some place on the send email screen.

* **What models will you have in your application?**
There will be a person model, song model, and Artist model.

* **What fields will each model have?**
Person- id, friends, song, username, password, email
Song- id, artist_id, title
Artist- id, songs, name

* **What uniqueness constraints will there be on each table? (e.g. can't add a song with the same title as an existing song)**
Person- you can't have the same username as one that already exists. You can't add an email that already exists as well.
Song- You can't add the same artist-song combination twice.
Artist- If the artist already exists, don't add them to the table

* **What relationships will exist between the tables? What's a 1:many relationship between? What about a many:many relationship?**
Person-Song will be a one to many (only the most recent song will be saved.)
Person-Person will be a many to many
Song-Artist will be a many to many

* **How many get_or_create functions will you need? In what order will you invoke them? Which one will need to invoke at least one of the others?**
I will need three get-or-create functions. one for each of the tables. The get-or-create-song will call get-or-create-artist. The get-or-create-person will call the get-or-create-song.

## The Pages

* **How many pages (routes) will your application have?**
My application will have 7 routes.

* **How many different views will a user be able to see, NOT counting errors?**
My application will have 5 different views

* **Basically, what will a user see on each page / at each route? Will it change depending on something else -- e.g. they see a form if they haven't submitted anything, but they see a list of things if they have?**
The main view will be a form prompting the user for a song name. Upon entering the name, they will be re-routed to a page with 5 different possible songs with that name. Next to each song will be two buttons: 'save and send' and 'save and continue'. On the buttom will be a prompt asking if none of the songs are the ones the user is looking for and a button to load more songs. Upon clicking save and send, the user will be taken to a page to login or create an account. After logging in, the user will be taken to a page that shows them all their friends, with the top friends being first and bolded. The user will then be able to choose which friend they would like to send the song to. There will be a link to another page in which a user can add more friends. This link will be available to the user on the home page as well once they have logged in. 

## Extras

* **Why might your application send email?**
So that users can share song interests with their friends.

* **If you plan to have user accounts, what information will be specific to a user account? What can you only see if you're logged in? What will you see if you're not logged in -- anything?**
You can enter a song if you are not logged in in order to see it's information. If you are logged in, you can see your friends, your most recent song search, and your username. 

* **What are your biggest concerns about the process of building this application?**
I do not really know how many to many relationships work in real time. am i supposed to manually add tables and rows or does this happen automatically? This is the only thing that really confuses me.
