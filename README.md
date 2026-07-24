# movie-recommendation-system-python 🎬 

A Python-based content recommendation engine that suggests movies based on similarity in titles and genres using **Jaccard similarity**. Users can search by movie or genre, view top recommendations, and analyze rating distributions over time.

## ✨ Features

- **Movie-Based Recommendations**: Find similar movies based on title and genre similarity using Jaccard similarity algorithm
- **Genre-Based Search**: Discover top-rated movies within a specific genre
- **Rating Distribution Analysis**: Visualize how ratings evolved over the first 10 years after a movie's release
- **Interactive User Interface**: Easy command-line interface for searching and browsing recommendations
- **Star Rating Conversion**: Display similarity scores as intuitive star ratings (0-5 stars)

## 🛠️ Technology Stack

- **Python 3.x**
- **Libraries**:
  - `pandas` - Data manipulation and analysis
  - `matplotlib` - Visualization of rating distributions
  - `ast` - Parsing genre data structures
  - `re` - Regular expression for year extraction

## 📋 Requirements

pandas matplotlib

Code

Install dependencies:
```bash
pip install pandas matplotlib
📊 Dataset
This project requires two CSV files:

movies.csv
Columns: movieId, title, genres
Description: Contains movie information with genres in JSON or pipe-separated format
ratings.csv
Columns: movieId, rating, timestamp
Description: Contains user ratings and timestamps (Unix timestamp format)
🚀 Usage
Run the Program
bash
python movieRecommendationSystem.py3.txt
Interactive Menu
The program will prompt you to choose between two options:

Option 1: Search by Movie
Code
Do you want to search by Movie or Genre? (Enter 'movie' or 'genre'): movie
Enter movie name with year (e.g., Toy Story (1995)): Toy Story (1995)
Output:

Top 5 movies similar to your selected movie
Similarity scores displayed as star ratings
Rating distribution charts for each recommendation
Option 2: Search by Genre
Code
Do you want to search by Movie or Genre? (Enter 'movie' or 'genre'): genre
Enter genre (e.g., Comedy, Drama): Comedy
Output:

Top 5 movies in the selected genre
Rating distribution charts for each movie
🧮 Algorithm Details
Jaccard Similarity
The recommendation system uses Jaccard similarity to compare movies:

Code
Jaccard Similarity = |Set1 ∩ Set2| / |Set1 ∪ Set2|
Where:

Set1: Tags (title + genres) of the query movie
Set2: Tags of comparison movies
Range: 0 (no similarity) to 1 (identical)
Rating Visualization
Scatter Plot: Individual ratings over time
Line Plot: Average rating trend
Time Range: First 10 years after movie release
📁 Project Structure
Code
MovieRecommendationSystem/
├── movieRecommendationSystem.py3.txt    # Main application script
├── movies.csv                            # Movie dataset
├── ratings.csv                           # Ratings dataset
└── README.md                             # This file
🔍 Key Functions
Function	Description
parse_genres(genres)	Extracts genre names from JSON or pipe-separated format
get_release_year(title)	Extracts release year from movie title
jaccard_similarity(set1, set2)	Calculates Jaccard similarity between two tag sets
similarity_to_stars(sim_score)	Converts similarity score to star rating (0-5)
plot_rating_distribution(movie_id, title)	Visualizes rating trends over time
recommend(movie)	Finds top 5 movies similar to input movie
recommend_by_genre(genre)	Finds top 5 movies in specified genre
📈 Example Output
Code
🎬 Top 5 Recommended Movies similar to 'Toy Story (1995)':
👉 Toy Story 2 (1999) (Score: 5/5)
👉 Toy Story 3 (2010) (Score: 4/5)
👉 Toy Story 4 (2019) (Score: 4/5)
👉 Finding Nemo (2003) (Score: 3/5)
👉 A Bug's Life (1998) (Score: 3/5)
⚠️ Error Handling
The program includes validation for:

Movies not found in dataset
Missing genres data
Missing timestamp information
No ratings available for a movie
Invalid user input
🔧 Customization
Modify Similarity Score Display
Change max_stars parameter in similarity_to_stars():

Python
similarity_to_stars(sim_score, max_stars=10)  # Display as out of 10
Adjust Time Window for Rating Analysis
Change the year window in plot_rating_distribution():

Python
movie_ratings = movie_ratings[movie_ratings['year'] <= release_year + 20]  # 20 years instead of 10
Change Number of Recommendations
Modify the slice in recommend() function:

Python
top5 = sorted(similarities, reverse=True, key=lambda x: x[1])[:10]  # Get top 10 instead of 5
🎯 Future Enhancements
 Collaborative filtering for user-based recommendations
 Machine learning models (KNN, content-based filtering)
 Web interface using Flask/Django
 Database integration for scalability
 User preference profiles and history
 Real-time rating updates
 Movie metadata caching for performance
📝 License
This project is open source and available for educational purposes.

👤 Author
Amrutha Varshini Purimitla

🤝 Contributing
Contributions are welcome! Feel free to:

Report bugs
Suggest new features
Improve documentation
Optimize algorithms
📞 Support
For issues or questions, please open an issue on the repository.

Happy Movie Watching! 🍿🎭
