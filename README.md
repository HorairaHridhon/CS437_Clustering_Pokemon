# Pokémon Clustering with K-Means

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset Description](#dataset-description)
3. [Prerequisites](#prerequisites)
4. [Installation Instructions](#installation-instructions)
5. [Project Goals](#project-goals)
6. [Code Explanation](#code-explanation)
7. [How to Run the Code](#how-to-run-the-code)
8. [Sample Output](#sample-output)
9. [License](#license)

---

## Project Overview

This project applies **K-Means clustering** to categorize Pokémon based on their fighting statistics. For each primary Pokémon type (e.g., Fire, Water), the appropriate number of clusters is determined by maximizing the **Silhouette Coefficient** score. The project leverages a **MinMaxScaler** to ensure fair scaling of the stats, preventing any bias due to varying stat magnitudes.

The clustering process helps in identifying groups of Pokémon with similar characteristics, making the insights applicable to real-world scenarios, such as team formation and game strategy development.

---

## Dataset Description

The dataset used is `Pokemon.csv`, containing the following columns:
- **Name**: Name of the Pokémon
- **Type 1**: The primary type of the Pokémon (e.g., Fire, Water)
- **HP**: Hit/health points (damage threshold before fainting)
- **Attack**: Strength of physical attacks
- **Defense**: Resistance to physical damage
- **Sp. Atk**: Strength of special (non-physical) attacks
- **Sp. Def**: Resistance to special damage
- **Speed**: Determines which Pokémon attacks first in a round

### Dataset Requirements
- **Columns used for clustering**: `HP`, `Attack`, `Defense`, `Sp. Atk`, `Sp. Def`, `Speed`
- **Excluded columns**: `Type 2`, `Name`, `Generation`, `Total`, `Legendary`

---

## Prerequisites

Ensure you have the following dependencies installed:

- Python 3.x
- Libraries:
  - `pandas`
  - `scikit-learn`

You can install the required libraries using the following command:

```bash
pip install pandas scikit-learn
```

---

## Installation Instructions

1. **Clone the repository**:

   ```bash
   git clone https://github.com/yourusername/pokemon-clustering.git
   cd pokemon-clustering
   ```

2. **Place the dataset**:

   Ensure the `Pokemon.csv` file is in the root directory of the project.

---

## Project Goals

1. **Cluster Pokémon** based on their stats using **K-Means**.
2. **Determine the optimal number of clusters** for each primary type by maximizing the **Silhouette Coefficient**.
3. **Output the clusters** along with mean statistics for each cluster.

---

## Code Explanation

### Key Sections of the Code

1. **Data Preparation**:
   - Load the dataset.
   - Select relevant columns for clustering.

2. **Pipeline Setup**:
   - Create a pipeline with `MinMaxScaler` and `KMeans`.

3. **Cluster Optimization**:
   - Iterate over each primary type and determine the optimal number of clusters (between 2 and 14).
   - Calculate and track the **Silhouette Coefficient** for each number of clusters.

4. **Output Generation**:
   - For each type, print the clusters along with Pokémon stats and cluster means.

### Key Libraries Used

- **pandas**: For data manipulation.
- **scikit-learn**: For scaling, clustering, and calculating silhouette scores.

---

## How to Run the Code

1. Ensure `Pokemon.csv` is in the same directory as the script.
2. Run the Python script:

   ```bash
   python clustering_pokemon.py
   ```

3. The output will display the silhouette scores for different cluster counts and the clusters for each Pokémon type.

---

## Sample Output

```
Fire
-----------
2 clusters: 0.41
3 clusters: 0.45
4 clusters: 0.47
best number of clusters: 4
best score: 0.47

Cluster 0
            Name   HP  Attack  Defense  Sp. Atk  Sp. Def  Speed
2     Charizard   78      84       78      109       85     100
10       Magmar   65      95       57      100       85      93
Mean HP: 71.5
Mean Attack: 89.5
Mean Defense: 67.5
Mean Sp. Atk: 104.5
Mean Sp. Def: 85.0
Mean Speed: 96.5
```

---

## License

This project is licensed under the MIT License.
