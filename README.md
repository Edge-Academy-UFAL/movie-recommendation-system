# Movie Recommendation System
![Movie Recommendation](images/movieimg.png)

## Table of Contents
- [Introduction](#introduction)
- [Content-Based Filtering](#what-is-content-based-filtering)
- [Dataset](#dataset)
- [Cosine Similarity](#cosine-similarity)
- [Examples](#examples)

## Introduction
The Movie Recommendation System is a project that aims to provide users with personalized movie recommendations based on their preferences. This system utilizes content-based filtering techniques to suggest movies to users that are similar to those they have already watched or liked.

## What is Content-Based Filtering?
Content-based filtering is a recommendation technique that focuses on the attributes of items to make suggestions. In the context of movies, this involves creating a profile for each movie based on its features, such as genres, cast, and plot keywords. The system then recommends movies that share similar attributes to those the user has already expressed interest in.

### Advantages of Content-Based Filtering
Content-based filtering offers some advantages:

1. **No Dependency on User Data:** Unlike collaborative filtering, content-based filtering doesn't rely on user behavior or preferences. It operates solely based on the item's attributes, making it especially useful for new users or when limited user data is available.

2. **Reduced Cold-Start Problem:** Content-based filtering can make recommendations for new items that have just been added to the system, even if there's no user interaction history with them. This addresses the "cold-start" problem that collaborative filtering struggles with.

3. **Transparency and Explanations:** Recommendations from content-based filtering are more explainable. Since suggestions are made based on item attributes, users can understand why a particular item is being recommended.

4. **Personalization:** Content-based filtering can offer personalized recommendations for niche or specific interests. It's capable of capturing unique user preferences that might not be prevalent in the broader user population.

## Dataset
The dataset used for this project is the [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata), which contains comprehensive information about movies including details like titles, genres, cast, plot keywords, overview and more. This dataset have many   features that allow us to create a detailed profile for each movie, enabling accurate content-based recommendations.

## Cosine Similarity
To quantify the similarity between movies, I used the cosine similarity metric. Cosine similarity measures the cosine of the angle between two non-zero vectors in an n-dimensional space. By calculating the cosine similarity between movie profiles, we can determine how closely related they are and provide recommendations based on those similarities.

## Examples
``` Python
recommend_movies('Guardians of the Galaxy', cosine_sim_matrix)
```
```
79                             Iron Man 2
182                               Ant-Man
16                           The Avengers
7                 Avengers: Age of Ultron
26             Captain America: Civil War
174                   The Incredible Hulk
31                             Iron Man 3
68                               Iron Man
126                  Thor: The Dark World
169    Captain America: The First Avenger
Name: original_title, dtype: object
```
``` Python
recommend_movies('The Dark Knight', cosine_sim_matrix)
```
```
119                               Batman Begins
3                         The Dark Knight Rises
10                             Superman Returns
9            Batman v Superman: Dawn of Justice
72                                Suicide Squad
163                                    Watchmen
1035                                  Jonah Hex
3854    Batman: The Dark Knight Returns, Part 2
299                              Batman Forever
303                                    Catwoman
Name: original_title, dtype: object
```