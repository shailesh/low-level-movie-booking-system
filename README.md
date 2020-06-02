##service for online movie booking.

Tools:

Django Rest Framework
Ajax Call
Bootstarp for UI
MySql Database

How to Run:

Clone the project
Create virtual env using python3 `virtualenv env --python=python3`
Activate env `source env/bin/activate`
Install required modules and lib `pip install requirements.txt`
Create DB in your local system
Run `python manage.py migrate` to migrate the schema to DB
Run local server: `python manage.py runserver`

These are the apps working inside:
  1. Theatre App 
  This list down all the theatre available city wise

Output: 
All theaters: url : http://localhost:8000/theatres/

{'paginator': None, 'page_obj': None, 'is_paginated': False, 'object_list': <QuerySet [<Theatre: PVR-No. 69, 4th Cross Manjunatha L-BANGALORE>]>, 'theatre_list': <QuerySet [<Theatre: PVR-No. 69, 4th Cross Manjunatha L-BANGALORE>]>, 'view': <theatre.views.TheatreListView object at 0x7f9e1259d190>, 'theatres': [[<Theatre: PVR-No. 69, 4th Cross Manjunatha L-BANGALORE>]]}

For one Theater, passing theater ID: URL: http://localhost:8000/theatres/1/
[[<Show: Back to the Future-PVR-No. 69, 4th Cross Manjunatha L-BANGALORE-2020-06-02-06:30:03>]]


  2. Movie App
  List down all the ongoing and upcoming movies in the specific theatre

 Output:
All Movies: URL: http://localhost:8000/movies/

 {'paginator': None, 'page_obj': None, 'is_paginated': False, 'object_list': <MovieQuerySet [<Movie: Back to the Future>, <Movie: Movie 1>]>, 'movie_list': [[<Movie: Back to the Future>, <Movie: Movie 1>]], 'view': <movie.views.MovieListView object at 0x7f6925d8cbe0>}


URL: http://localhost:8000/movies/1/
Output: 
[[<Show: Back to the Future-PVR-No. 69, 4th Cross Manjunatha L-BANGALORE-2020-06-02-06:30:03>]] Back to the Future



  3. booking app

  After selecting the movie this funtion allows it to make the booking
  this displays all the bookings done
URL : http://localhost:8000/booking/seatchoice/1/
Output: form for type of seats Premium, gold and silver


URL: http://localhost:8000/booking/payment/
Output: A11,A12 Back to the Future-PVR-No. 69, 4th Cross Manjunatha L-BANGALORE-2020-06-02-06:30:03 600 Platinum `seat_stseat_str, show, ticket_price, seat_typer, show, ticket_price, seat_type`


  4. Home App
  This stores all kind of users like super user, staff and end users 
  I've used custom user model rather than default user model.

 POST METHOD:
 Only for user register for now due to minimal time given
 No any post methods for listing the movie or theaters. Can be done by any Super Admin visiting the django admin dashboard like, listing the movie, seats, theaters, ...

 LIST METHOD:
 Listing the Movie, theaters, seats, and so on.

 Response:
 Have rendered all the reponse to specific page, can be exposed to end clients by creating a new table for client and storing client ID. For every API using decorators to verify the cleint type and pass the list of movie, price, theaters and so on.. Given enough time I can implement this too. 
 
 SEARCH :

 Realtime search query based on input text there is ajax call no need to click on the search button.

SCREENSHOTS: Have attached the screenshot for diffrent working pages from Django admin to booking