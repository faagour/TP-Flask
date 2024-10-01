FROM python
WORKDIR /app
COPY requirements.txt /app
RUN pip install -r requirements.txt
ADD . /app/
CMD ["python","-u","movie.py"]


"""
openapi: 3.0.0
info:
  title: Movie Service API
  version: 1.0.0
  description: A simple API for managing a movie collection
servers:
  - url: http://192.168.145.229:3200
paths:
  /:
    get:
      summary: Welcome to the Movie service
      responses:
        '200':
          description: Welcome message
          content:
            text/html:
              schema:
                type: string
  /json:
    get:
      summary: Get all movies in JSON format
      responses:
        '200':
          description: List of all movies
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    title:
                      type: string
                    genre:
                      type: string
                    year:
                      type: integer
  /addmovie/{movieid}:
    post:
      summary: Add a new movie
      parameters:
        - name: movieid
          in: path
          required: true
          schema:
            type: integer
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              properties:
                id:
                  type: integer
                title:
                  type: string
                genre:
                  type: string
                year:
                  type: integer
      responses:
        '200':
          description: Movie added
        '409':
          description: Movie ID already exists
        '415':
          description: Unsupported media type
  /movies/{movieid}:
    get:
      summary: Get movie details by ID
      parameters:
        - name: movieid
          in: path
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: Movie details
        '404':
          description: Movie ID not found
  /movies/genre/{genre}:
    get:
      summary: Get movies by genre
      parameters:
        - name: genre
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: List of movies by genre
        '404':
          description: No movies found for the specified genre
  /movies/year/{year}:
    get:
      summary: Get movies by year
      parameters:
        - name: year
          in: path
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: List of movies by year
        '404':
          description: No movies found for the specified year
  /movies/title/{title}:
    get:
      summary: Search for movies by title
      parameters:
        - name: title
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: List of movies matching the title
        '404':
          description: No movies found with the specified title
  /deletemovie/{movieid}:
    delete:
      summary: Delete a movie by ID
      parameters:
        - name: movieid
          in: path
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: Movie deleted
        '404':
          description: Movie ID not found
  /help:
    get:
      summary: Get a list of all available endpoints
      responses:
        '200':
          description: List of all available endpoints
          content:
            application/json:
              schema:
                type: object


ca c'etait pour ajouter le fichier de la vidéo à notre bd:


    ##curl -X POST http://192.168.145.229:3200/addmovie/14 -H "Content-Type: application/json" -d '{"id": 14, "title": "Inception", "genre": "Sci-Fi", "year": 2010}'



"""