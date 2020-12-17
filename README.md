# **SMM638 - Network Analytics (Final Project)**

## Introduction

This final course project deals with the topics of homophily, closure, and
performance. There is consistent evidence that selection and socialization
mechanisms – as the vessels of homophily – vastly affect entities' choices
such as partner selection, hiring, collaboration, or consumption. What is less
clear is how selection and socialization impact an entity's performance by
influencing the decision making process.

## Problem to address

Address the following questions:

- (to what extent) is homophily present in the network dataset at hand?
- then, how does homophily relate to entity's performance?

## Background for the case study

To deliver the project, students may want to rely upon the following concepts
and tools:

- theoretical concept of homophily
- homophily-related network mechanisms: selection and socialization
- empirical implementations of the homophily framework

## **Dataset**
- [Github Repo: `ewenme/trasnfers`](https://github.com/ewenme/transfers)   
Data on European football clubs' player transfers, through 1992/93 to 2020/21 seasons (as found on Transfermarkt).
- [Kaggle: European Soccer Database](https://www.kaggle.com/hugomathien/soccer)  
25k+ matches, players & teams attributes for European Professional Football from 2008 to 2016.

## **Directory Structure**

```
        net-analytics-ftp
        ├── README.md
        ├── .gitignore
        ├── requirements.txt
        ├── datasets
        │   ├── raw_data
        │   │   ├── fifa_data.tar.gz
        │   │   ├── 1992
        │   │   |    ├── dutch_eredivisie.csv
        │   │   |    ├── english_championship.csv
        │   │   |    ├── english_premier_league.csv
        │   │   |    ├── french_ligue_1.csv
        │   │   |    ├── italian_serie_a.csv
        │   │   |    ├── portugese_liga_nos.csv
        │   │   |    ├── russian_premier_liga.csv
        │   │   |    └── spanish_primera_division.csv
        │   │   ├── 1993
        │   │   ├──  .
        │   │   ├──  .
        │   │   └── 2020
        │   └── cleaned_data
        |       ├── node_edge_data.csv
        |       ├── perf_eval_table.csv
        |       ├── player_rating.csv
        |       └── top_player_fifa.csv
        └── scripts
            ├── 00_extract_data_from_db.ipynb
            ├── 01_data_preprocessing.ipynb
            ├── 02_analysis.ipynb
            └── output
                ├── simul_k_pk.csv
                ├── adj_coef.png
                ├── fee_age_bivar.png
                ├── fee_hist.png
                ├── homo-perf.png
                ├── homo-tenure.png
                ├── homophily.png
                ├── hypo_test.png
                ├── poly_smooth.png
                ├── top_homo-perf.png
                └── top_homo-tenure.png

```

## File Description
-   `requirements.txt` -> Python packages requirements

### datasets
#### raw_data
-   `fifa_data.tar.gz` -> `.tar.gz` file contains database of football data retrieved from [Kaggle: European Soccer Database](https://www.kaggle.com/hugomathien/soccer)  
-   Folders: `1992` - `2020` -> Folders contain `.csv` files of football data from the nine major leagues retrieved from [Github Repo: `ewenme/trasnfers`](https://github.com/ewenme/transfers) 
#### cleaned_data
-   `node_edge_data.csv` -> Table contains all data from [Github Repo: `ewenme/trasnfers`](https://github.com/ewenme/transfers) used to analyze homophily (membership closure) and tenure analysis
-   `perf_eval_table.csv` -> Table contains only player transfer data related to buy-sell of contract used to analyze performance-homophily
-   `top_player_fifa.csv` -> Table contains list of top players based on Fifa data from [Kaggle: European Soccer Database](https://www.kaggle.com/hugomathien/soccer)  

### scripts
-   `00_extract_data_from_db.ipynb` -> ETL process to prepare `top_player_fifa.csv` file
-   `01_data_preprocessing.ipynb` -> Data preprocessing to create `node_edge_data.csv` and `perf_eval_table.csv` files
-   `02_analysis.ipynb` -> All analyses including Fee-Age analysis, Homophily analysis, Null case simulation and hypothesis testing, Homophily-Performance analysis, Tenure analysis, and Top player analysis

### output
-   `simul_k_pk.csv` -> k-pk table generated from 10 simulated data
-   `adj_coef.png` -> Plot of age-adjustment coefficients
-   `fee_age_bivar.png` -> Bivariate plot of average fee and age
-   `fee_hist.png` -> Univariate plot of fee (histogram)
-   `homo-perf.png` -> Line plot to demonstrate the relationship between homophily and performance
-   `homo-tenure.png` -> Line plot to demonstrate the relationship between homophily and tenure
-   `homophily.png` -> Line plot to demonstrate the relationship between k and p(k)
-   `hypo_test.png` -> Visualization to illustrate the result of hypothesis testing
-   `poly_smooth.png` -> Chart to show how we smooth age variable
-   `top_homo-perf.png` -> Line plot to demonstrate the relationship between homophily and performance for top players
-   `top_homo-tenure.png` -> Line plot to demonstrate the relationship between homophily and tenure for top players
