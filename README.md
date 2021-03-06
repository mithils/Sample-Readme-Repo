# SI 364 - Winter 2018 - Final Project

## My project

In this project:
* An instructor of a class where projects are due can log in and submit to a form
    * A word representing the theme of the student's project (e.g. `movies` or `food`)
    * The name of the student's project
    * The student's name
* On the submission, the word representing the theme of the student project is searched on Flickr for 10 photos
* Three random photos from that search are saved to the database and associated with that project
* The application saves: each entered student, each entered project, and photos
* Allows each logged-in user (an instructor) to see all of the students they've entered, and the associated projects and photos (see navigation in the application)
* One logged in instructor cannot see another logged in instructor's students or the students' projects

## Requirements
### Installations:

* `flask` library and all `flask`-related modules we have used in SI364
* The module `flickrapi` must be pip installed

### Other

* You must have a file called `flickr_api_data.py` in the same directory as the `SI364final.py` file, of the same format as the one included, but with API key filled in. You can get an API key at <THIS URL>.
* NOTE: A sample file with API keys is included in a file on Canvas for SI 364, so as not to include it on GitHub. (Of course, this repository is private, but just in case I decide to change that, I am not committing any API keys to GitHub!)

## What to do to run this application

* `cd` to the directory in which the app files live
* run, in Python `python SI364final.py runserver`
* You should see a home page prompting you to log in or register
* Log in (register if you don't have an account, and then log in)
* You should see a form prompting you for a student name and a word representing the theme of their project
    * For example, type `Jackie Cohen` into the first box and `photos` into the second box.
    * You should be redirected to a page that renders photos, and can use the navigation to see other pages!

## Routes in this application

* `/index` -> `index.html`
* `/all_photos` -> `all_photos.html` (login restricted)
* `/all_searches` -> `searches.html` (login restricted)
* `/your_students` -> `students.html` (login restricted)
* `/projects` -> `projects.html` (login restricted)
* `/student/<name>` -> `specific_student.html` (login restricted)
* `/project/<ident>` -> `specific_project.html` (login restricted)


## Differences from my midterm

My midterm allowed an instructor to enter a student name and name of the student's project, but this application has a brand new set of API requests, thus saving information that the midterm didn't save about Flickr photos, and this app saves more information about each student project. There is also a new relationship between projects and photos, and between photos and search terms, neither of which existed in my midterm, so I have built up all of the midterm components to make them different and/or more complicated.

## Requirements to complete for 2880 points (90%) -- an awesome, solid app

### Note that I've bolded AND checked off all of the requirements I DID complete, and left alone the requirements that I did not, in a clear, readable way TODO TODO TODO

### **Documentation README Requirements**

- [x] **Create a `README.md` file for your app that includes the full list of requirements from this page. The ones you have completed should be bolded or checked off.**

- [x] **The `README.md` file should use markdown formatting and be clear / easy to read.**

- [x] **The `README.md` file should include a 1-paragraph (brief OK) description of what your application does**

- [x] **The `README.md` file should include a detailed explanation of how a user can user the running application (e.g. log in and see what, be able to save what, enter what, search for what... Give us examples of data to enter if it's not obviously stated in the app UI!)**

- [x] **The `README.md` file should include a list of every module that must be installed with `pip` if it's something you installed that we didn't use in a class session. If there are none, you should note that there are no additional modules to install.**

- [x] **The `README.md` file should include a list of all of the routes that exist in the app and the names of the templates each one should render OR, if a route does not render a template, what it returns (e.g. `/form` -> `form.html`, like [the list we provided in the instructions for HW2](https://www.dropbox.com/s/3a83ykoz79tqn8r/Screenshot%202018-02-15%2013.27.52.png?dl=0) and like you had to on the midterm, or `/delete -> deletes a song and redirects to index page`, etc).**

### Code Requirements

- [x] **Ensure that your `SI364final.py` file has all the setup (`app.config` values, import statements, code to run the app if that file is run, etc) necessary to run the Flask application, and the application runs correctly on `http://localhost:5000` (and the other routes you set up).**

- [x] **A user should be able to load `http://localhost:5000` and see the first page they ought to see on the application.**

- [x] **Include navigation in `base.html` with links (using `a href` tags) that lead to every other page in the application that a user should be able to click on. (e.g. in the lecture examples from the Feb 9 lecture, [like this](https://www.dropbox.com/s/hjcls4cfdkqwy84/Screenshot%202018-02-15%2013.26.32.png?dl=0) )**

- [x] **Ensure that all templates in the application inherit (using template inheritance, with `extends`) from `base.html` and include at least one additional `block`.**

- [x] **Must use user authentication (which should be based on the code you were provided to do this e.g. in HW4).**

- [x] **Must have data associated with a user and at least 2 routes besides `logout` that can only be seen by logged-in users.**

- [x] **At least 3 model classes *besides* the `User` class.**

- [x] **At least one one:many relationship that works properly built between 2 models.**

- [x] **At least one many:many relationship that works properly built between 2 models.**

- [x] **Successfully save data to each table.**

- [x] **Successfully query data from each of your models (so query at least one column, or all data, from every database table you have a model for) and use it to effect in the application (e.g. won't count if you make a query that has no effect on what you see, what is saved, or anything that happens in the app).**

- [x] **At least one query of data using an `.all()` method and send the results of that query to a template.**

- [x] **At least one query of data using a `.filter_by(...` and show the results of that query directly (e.g. by sending the results to a template) or indirectly (e.g. using the results of the query to make a request to an API or save other data to a table).**

- [x] **At least one helper function that is *not* a `get_or_create` function should be defined and invoked in the application.**

- [x] **At least two `get_or_create` functions should be defined and invoked in the application (such that information can be saved without being duplicated / encountering errors).**

- [ ] At least one error handler for a 404 error and a corresponding template.

- [ ] At least one error handler for any other error (pick one -- 500? 403?) and a corresponding template. -- Oops, I forgot these and didn't do them. So I haven't bolded them :(

- [x] **Include at least 4 template `.html` files in addition to the error handling template files.**

- [x] **At least one Jinja template for loop and at least two Jinja template conditionals should occur amongst the templates.**

- [x] **At least one request to a REST API that is based on data submitted in a WTForm OR data accessed in another way online (e.g. scraping with BeautifulSoup that *does* accord with other involved sites' Terms of Service, etc).**

 - [x] **Your application should use data from a REST API or other source such that the application processes the data in some way and saves some information that came from the source *to the database* (in some way).**

- [ ] At least one WTForm that sends data with a `GET` request to a *new* page.

- [x] **At least one WTForm that sends data with a `POST` request to the *same* page. (NOT counting the login or registration forms provided for you in class.)**

- [x] **At least one WTForm that sends data with a `POST` request to a *new* page. (NOT counting the login or registration forms provided for you in class.)**

- [x] **At least two custom validators for a field in a WTForm, NOT counting the custom validators included in the log in/auth code.**

- [x] **Include at least one way to *update* items saved in the database in the application (like in HW5).**

- [x] **Include at least one way to *delete* items saved in the database in the application (also like in HW5).**

- [x] **Include at least one use of `redirect`.**

- [x] **Include at least two uses of `url_for`. (HINT: Likely you'll need to use this several times, really.)**

- [x] **Have at least 5 view functions that are not included with the code we have provided. (But you may have more! *Make sure you include ALL view functions in the app in the documentation and navigation as instructed above.*)**


## Additional Requirements for additional points -- an app with extra functionality!

**Note:** Maximum possible % is 102%.

- **[x] (100 points) Include a use of an AJAX request in your application that accesses and displays useful (for use of your application) data.**
- [ ]  (100 points) Create, run, and commit at least one migration.
- [ ] (100 points) Include file upload in your application and save/use the results of the file. (We did not explicitly learn this in class, but there is information available about it both online and in the Grinberg book.)
- [ ]  (100 points) Deploy the application to the internet (Heroku) — only counts if it is up when we grade / you can show proof it is up at a URL and tell us what the URL is in the README. (Heroku deployment as we taught you is 100% free so this will not cost anything.)
- **[x]  (100 points) Implement user sign-in with OAuth (from any other service), and include that you need a *specific-service* account in the README, in the same section as the list of modules that must be installed.**


All set!
