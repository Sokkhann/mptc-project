# Movie Rating

Movie Rating is a web application that allows users to rate, review, and add movies to their favorite list. The application retrieves movie data from the TMDB API and integrates with a custom API built with Spring Boot to handle user interactions like ratings, reviews, and favorites.

## Features

- **Movie Listing**: Displays movies fetched from the TMDB API.
- **Rate Movies**: Users can rate movies on a scale of 0.5 to 10.
- **Review Movies**: Users can write reviews for movies, with input validation to ensure proper content.
- **Favorite Movies**: Users can add or remove movies from their favorite list.
- **Review Filtering**: Reviews can be filtered to display the latest reviews on top for a better user experience.

## Technologies Used

- **Frontend**: Vue.js
- **Backend**: Spring Boot (Java)
- **Database**: MongoDB
- **API**: TMDB (The Movie Database API)
- **Docker**: Containerization of all services using Docker Compose

## Features in Detail

### User Features:
- **Rate Movies**: Users can rate movies between 0.5 and 10. The system ensures that ratings are valid and stores them in the database.
- **Review Movies**: Users can add reviews for movies. Reviews are validated before submission to ensure proper content (e.g., no empty reviews). Reviews are listed in descending order of submission time.
- **Add/Remove Favorites**: Users can mark movies as favorites and remove them at any time. Favorite movies are stored in the user's profile.
- **Movie Details**: Each movie fetched from TMDB includes details like title, description, genre, and rating, along with an option to see all user reviews.

### Admin Features (If applicable):
- **Manage Movies**: Admins can add or remove movies from the platform, although the primary source is the TMDB API.
- **Moderate Reviews**: Admins can remove inappropriate reviews if necessary.

## Project Structure
```
Movie-Rating
   ├── backend/
   │ ├── src/
   │ │ ├── main/
   │ │ │ ├── java/
   │ │ │ └── resources/
   │ ├── Dockerfile
   │ └── pom.xml
   │
   ├── movie-rating/
   │ ├── src/
   │ │ ├── assets/
   │ │ ├── components/
   │ │ ├── views/
   │ │ └── App.vue
   │ ├── Dockerfile
   │ └── package.json
   │
   ├── docker-compose.yml
   ├── README.md
   └── .gitignore
```


## Directory Overview

### `backend/`
- **src/**: Contains the source code for the backend application.
  - **main/**: Primary directory for backend logic.
    - **java/**: Java source files.
    - **resources/**: Configuration files, static resources, etc.
- **Dockerfile**: Defines the Docker image for the backend service.
- **pom.xml**: Maven configuration file for dependency management and build processes.

### `movie-rating/`
- **src/**: Contains the frontend source code.
  - **assets/**: Static assets like images, stylesheets, etc.
  - **components/**: Reusable Vue.js components.
  - **views/**: Page-level Vue.js components.
  - **App.vue**: Root Vue component for the frontend application.
- **Dockerfile**: Defines the Docker image for the frontend service.
- **package.json**: Node.js project metadata and dependency management file.

### `docker-compose.yml`
- Configuration file for orchestrating multiple Docker containers (e.g., frontend, backend, database).

### `README.md`
- Documentation file providing an overview of the project, setup instructions, and usage guidelines.

### `.gitignore`
- Specifies files and directories to be ignored by Git version control.

---

## Getting Started

### Prerequisites
Ensure you have the following installed on your machine:
- Docker
- Docker Compose

### Installation and Setup

1. **Navigate to the project directory**:
   ```bash
   cd movie-rating
### Frontend (`movie-rating`):
- Built using Vue.js and fetches movie data from the TMDB API.
- Components for rating, reviewing, and favoriting movies.
- Displays movie details and reviews in a user-friendly layout.

### Backend (`backend`):
- Built with Spring Boot and handles the logic for managing ratings, reviews, and favorites.
- Integrates with MongoDB to persist user data and movie-related interactions.
- Exposes RESTful APIs for managing reviews, favorites, and ratings.

### Docker Setup:
- The entire application is containerized using Docker Compose.
- Each service (frontend, backend, and MongoDB) runs in its own container.

## Access the Application

- **Frontend**: [http://localhost:5173](http://localhost:5173)
- **Backend**: [http://localhost:8080](http://localhost:8080)
## API Endpoints

The backend provides the following RESTful API endpoints:

- **GET `/movies`**: Fetch a list of movies from TMDB.
- **POST `/movies/{movieId}/rating`**: Rate a movie (rating range: 0.5 to 10).
- **POST `/movies/{movieId}/review`**: Add a review for a movie.
- **GET `/movies/{movieId}/reviews`**: Get all reviews for a specific movie, sorted by the latest.
- **POST `/favorites`**: Add a movie to the user's favorite list.
- **DELETE `/favorites/{movieId}`**: Remove a movie from the user's favorite list.
   
