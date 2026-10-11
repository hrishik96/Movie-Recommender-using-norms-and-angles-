# Norms, Angles, and Your Movie Choices

A movie recommendation mini-project exploring how concepts from **linear
algebra** can be used to compare users' movie preferences and recommend
movies they may like.

## Project Overview

This project demonstrates a simple recommender system using vectors,
norms, inner products, similarity measures, projection, and
least-squares approximation.

It has two parts:

-   **Part A --- Controlled example:** Uses a small, predefined
    user--movie ratings matrix to demonstrate the mathematics and
    predict ratings hidden from the target user.
-   **Part B --- MovieLens example:** Applies the approach to the
    MovieLens Latest-Small dataset, compares users based on movies they
    have both rated, and generates recommendations for movies the target
    user has not rated.

## Concepts Used

-   **Vectors and norms:** Represent each user's movie ratings as a
    vector and calculate Euclidean distance between users.
-   **Dot product and cosine similarity:** Compare the direction of
    users' rating vectors to estimate preference similarity.
-   **Pearson correlation:** Compare how users' ratings vary relative to
    their own average ratings.
-   **Projection:** Find the component of one vector along another
    vector.
-   **Least-squares approximation:** Estimate coefficients that best fit
    a target user's known ratings using ratings from reference users.
-   **RMSE (Root Mean Squared Error):** Measure the difference between
    predicted and known ratings in the controlled example.

## How It Works

1.  Represent users and their movie ratings as vectors.
2.  Compare users using distance and similarity measures.
3.  Hide selected ratings in the controlled example to create a
    prediction task.
4.  Select reference users and use least squares to estimate their
    contribution to the target user's known ratings.
5.  Use the estimated coefficients to predict the hidden ratings, then
    clip predictions to the rating range of 1--5.
6.  In the MovieLens part, identify similar users and rank unrated
    movies using predicted ratings.

> **Note:** Least-squares coefficients are fitted weights; they should
> not be interpreted as percentages or similarity scores. RMSE is an
> error metric, not an accuracy percentage. The controlled example's
> RMSE is calculated on the known ratings used for fitting, so it is not
> by itself a measure of performance on unseen test data.

## Dataset

### Part A: Controlled dataset

A small, predefined ratings matrix makes the calculations and
predictions easy to inspect. The example hides the target user's ratings
for **Toy Story** and **Frozen**.

### Part B: MovieLens Latest-Small

The second part attempts to download the MovieLens Latest-Small dataset
from GroupLens:

-   Dataset page: https://grouplens.org/datasets/movielens/latest/
-   Download URL used by the notebook:
    https://files.grouplens.org/datasets/movielens/ml-latest-small.zip

The implementation reduces the dataset to a subset of users and movies
for analysis. Internet access is required for the download step. If the
download fails because of a network or environment restriction, the
MovieLens section may not run until the dataset is available.

## Requirements

-   Python 3
-   NumPy
-   Pandas
-   Matplotlib

The MovieLens section also uses Python's built-in `urllib.request`,
`zipfile`, and `io` modules.

Install the main packages with:

``` bash
pip install numpy pandas matplotlib
```

## Run the Project

### Option 1: Google Colab

1.  Open the `.ipynb` notebook in Google Colab.
2.  Run the cells from top to bottom.
3.  Allow the MovieLens download cell to access the internet if you want
    to run Part B.

### Option 2: Run the Python script locally

1.  Download or clone this repository.
2.  Install the requirements listed above.
3.  Run the script:

``` bash
python norms_angles_and_your_movie_choices.py
```

If your repository uses a different Python filename, replace the
filename in the command with the actual script name.

## Repository Contents

-   `norms_angles_and_your_movie_choices.ipynb` --- notebook version,
    suitable for viewing code cells, outputs, tables, and plots.
-   `norms_angles_and_your_movie_choices.py` --- Python script version,
    if included in the repository.
-   `README.md` --- project overview and instructions.

Keep only the filenames that are actually present in your GitHub
repository, and adjust them if your downloaded files have different
names.

## Limitations

-   The controlled dataset is small and illustrative; its results should
    not be treated as a reliable real-world recommendation benchmark.
-   The MovieLens implementation uses a reduced subset of users and
    movies rather than the full dataset.
-   Users may have rated different movies, so the MovieLens comparison
    considers overlapping ratings.
-   Predictions are constrained to the 1--5 rating range.
-   Results depend on the chosen reference users, available ratings, and
    dataset subset.

## Acknowledgement

This mini-project is based on the linear algebra project **"Norms,
angles, and your movie choices"**, which explores using norms and inner
products for a simple recommender system. The implementation extends the
basic idea with cosine similarity, projection, least-squares prediction,
RMSE evaluation, and a MovieLens example.

## Team
Hrishik N Urs ,
Hriday Kamath ,
Jivesh R M ,
Harsha C K
