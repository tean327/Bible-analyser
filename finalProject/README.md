BIBLE THERAPY
This project is a web app made with HTML, CSS, JavaScript, Flask, Python and SQL
The pitch is that as a Christian you can sometimes feel some emotions and that you want encouragement. But what if you don’t know which verses to look for. Then this app is for you, there are some buttons with emotions on them, you click what emotion you are currently feeling, and you will find some verses to help you in your current situation.
How does the webpage work?
The idea is simple, the user comes as he is, if he is feeling a particular emotion, he clicks at these emotions and the app outputs some verses to help the user in his situation and to help him meditate on how to surpass his emotions.
For now, I have implemented these emotions:
-Anxiety: Because a lot of people, me included, can feel overwhelmed with life or scared for their future, this is my case, so that with these verses they can relax on find ways to help them to overcome their anxiety!
-Patience: Same principle a lot of people can be impatient or don’t understand God’s plan for their life; by clicking on this emotion you will be outputted of verses to help you understand why God’s plan is perfect for your life and maybe also why your blessings don’t come right away
-Temptation: Everybody has been tempted in this life, that’s why we all need to know what to do when where are tempted, this list of verses will help you to do this.
-Joy: Even if life is hard, we all can be joyful that’s why I put this emotions, a lot of people will go to the lord only when they are not feeling good or they want something, this emotions will output a list of verses to help you either feel more joyful, or tell you what to do when you are feeling joyful because it is not that obvious
-Hope: Because we all need hope in our life
Once you have selected an emotion and read/meditate the different verses you can return to the 	“select an emotion” page and select another one.
I have also implemented a login page though you are not obliged to log in to access the app, once you have logged in you can access a button where you can send me an email at: bibletherapyapp@gmail.com

Routing
There is a route for each emotion, one for the page where you select your emotion, 	also one for the title page and with which route the user is in, the web app will do an SQL query for the emotions. Ex: if you click on anxiety this will be the query:
db.execute(“SELECT name, chapter, verse, text FROM MKJV_verses JOIN MKJV_books ON MKJV_books.id = MKJV_verses.book_id WHERE text LIKE "% worry %" OR text LIKE "% anxieties %" OR text LIKE "%take no thought%")
Database:
I download a database that stores the full MKJV bible inside two tables
The first one is the book table with two columns: an id, and the book name.
The second table is the verses table with 	5 columns an id, a book_id, a chapter for the chapter number, a verse for the number of the verse, and a text for the content of the verse.
I downloaded this bible database from here: https://github.com/scrollmapper/bible_databases/blob/master/formats/sqlite/MKJV.db
This project has two folders, a folder called static with the icon of the web page and the css file, a folder templates with all of my html files. These two folders are called like that because I’m using the Flask framework which needs to have these two folders called exactly like that to work correctly. I also have a file called app.py, it’s in this file that I do all of my routing and SQL’s queries and I also have two .db files one which is the bible database I was talking about and the second which is a user database made to stock the different emails from the user so that I can check if the email has already registered or no.
Demonstration on youtube
For the CS50 final project you must make a video showing your project, you can find it here:
https://youtu.be/6h_miTP3thY
How I want to improve this app:
In the future I want to make a part of my app where you can read the bible normally, but I also want to put in place a way where you have a list of favorite verses and that you can add every verse you came onto to your favorites
