# task-3
simple movie recommendation system
class Movie:
    def __init__(self, title, genre):
        self.title = title
        self.genre = genre

def content_based_recommendation(user_preferences, movies):
    recommended_movies = []
    for movie in movies:
        if any(genre in user_preferences for genre in movie.genre):
            recommended_movies.append(movie.title)
    return recommended_movies

# Example usage
movies = [Movie("Movie1", ["Action", "Adventure"]),
          Movie("Movie2", ["Drama", "Romance"]),
          Movie("Movie3", ["Action", "Thriller"])]

user_preferences = ["Horror", "Action"]

recommendations = content_based_recommendation(user_preferences, movies)
print("Recommended movies:", recommendations)
