We created a movie recommender app (web). Work based on the following:

+ previously generated data* (check data folder):
	- matrices-  movies_genres, movies_clusters_rating, user_item_matrix, etc.  as csv files
	- nmf (Non-Negative Matrix Factorization) models

+ the application files (check python, readme.md & requirements.txt files):
	-application.py,  utils.py, recommender.py
            
+ the web page files (hmtl +css & other):
	-templates folder: landing_page.html & recommender.html
	-static folder: movies_image.jpeg  styling_with_ccs.css


#This is how we did it:
# Create a Object-Oriented-Programming module
- We create a class called `MovieRecommender`
- The class accepts the following arguments:
  - `method`: string
  - `rated_movies`: rated movie list
  - `ratings`: ratings list
  - `n_movies`: no. of movies to return
- Class methods:
  - `get_recommendations()`: This is where all recommenders are implemented. 
  - All recommenders are imported from `utils.py` which also has a function that converts 2 lists into one dictionary as required by all the methods.

  # Flask
  - We created `application.py` file
  - add 2 functions:
    - Welcome for the landing page
    - recommender for the recommender page
    - We run the application.py file using debug=True and open the link in the browser
    - We modify the 2 returned objects to html
    - We create the templates folder and create the index.hmtl and recommender.html and format them to take a html standard convention
    - We import `render_template`  to allow html rendering and to carry along key-value pairs to the html page.
    - We include Jinja tags `{}` to enclose variables that are carried from the application.py file to the html pages
    - We learn how to loop with jinja tags
      - {% for i in values %}
      - ...
      - {% endfor}
    - We then do away with static user input and create a form with movie titles and ratings in the index.html file
    - We import the `request` method from flask to allow us to make `post` and `get` requests
    - We implement the submission of input from the user and catch the output
    - We then pass the outputs to the recommender python file as expected and make recommendations
    - We observe the recommendations with a message on which method was selected
  - We use `css` styling to beautify the page.

General instructions (from terminal):
- After you've cloned the repository git_clone git@github.com:IonelS-coder/movie_recommender_app.git)
- open the movie_recommender_app folder (e.g. cd movie_recommender_app)
- check the tree stucture (e.g. tree), you should see something similar to this:


├── application.py
├── data
│   ├── movies_clusters_complete.csv
│   ├── movies_clusters_ratings.csv
│   ├── movies.csv
│   ├── movies_genres.csv
│   ├── nmf_100.bin
│   ├── README.md
│   └── user_item_matrix.csv
├── README.md
├── recommender.py
├── requirements.txt
├── static
│   ├── movies_image.jpeg
│   ├── styling_with_ccs.css
│   └── WallpaperDog-11036502.jpg
├── templates
│   ├── landing_page.html
│   └── recommender.html
└── utils.py


