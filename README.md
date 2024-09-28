# ClusterPub

ClusterPub is a tool developed to help researchers in their processes of bibliographic review, 
helping them to find papers related to their areas of interest,
based on search results returned by papers repositories, like, IEEE Xplore and Pubmed.

## Instalation 🛠

To install and execute ClusterPub it is necessary to execute the following commands:

### Programming Language 💻

ClusterPub was developed using Python 3.11, to install it execute the commands bellow:

#### First update linux packages

```bash Python installation command
sudo apt update
```

#### Add Python packages repository
```bash Python installation command
sudo add-apt-repository ppa:deadsnakes/ppa
```

#### Install Python 3.11
```bash Python installation command
sudo apt install python3.11
```


### Poetry Package Manager 📦

#### Install pipx
```bash Python installation command
python3 -m pip install --user pipx
python3 -m pipx ensurepath
```

#### Install Poetry
```bash Python installation command
pipx install poetry
```


### Install dependencies 📦

OBS: Run the following commands inside the project directory.

#### Define Python env version
```bash Python installation command
poetry env use 3.11
```

#### Create Python virtual environment
```bash Python installation command
poetry shell
```

#### Install dependencies
```bash Python installation command
poetry install
```

## Run ClusterPub 🚀

To execute ClusterPub run the following command:

#### Cluster publications present in a bibliographic file
```bash Python installation command
python cluster_pub/main.py {source_file} {result_file}
```

#### OBS: The result_file name should contain the desired extension.

The allowed extensions for the source file are:

- NBIB
- RIS
- BibTex

The allowed extensions for the result file are:

- EPS
- JPEG
- PDF
- PGF
- PNG
- PS
- Raw (Binary)
- RGBA
- SVG
- SVGZ
- TIF
- TIFF
- Webp


#### To obtain help about the parameters and options available execute the following command:
```bash Python installation command
python cluster_pub/main.py --help
```

There is a folder in the project directory called sample_files, containing files that could be used to execute tests.

## Extract Clustering Metrics  📈

To calculate clustering metrics, like, Silhouette Score, Davies-Bouldin Score and Calinski-Harabasz Score run the following commands:

OBS: The argument number_of_clusters is not the desired clusters quantity,
but it is the quantity of clusters/categories that might exit in the analysed dataset.

#### Calculate Davies-Bouldin Score
```bash Python installation command
python cluster_evaluation.py davies_bouldin_score {source_file} {number_of_clusters}
```

#### Calculate Calinski-Harabasz Score
```bash Python installation command
python cluster_evaluation.py calinski_harabasz_score {source_file} {number_of_clusters}
```

#### Calculate Silhouette Score
```bash Python installation command
python cluster_evaluation.py silhouette_score {source_file} {number_of_clusters} --distance-metric={distance_metric}
```

#### To obtain help for the score commands listed above run the following command:
```bash Python installation command
python cluster_evaluation.py {score_command} -- help
```

## Background Information 🔍

The default hyperparameters and algorithms used in this project are:

- Word Embeddings Technicque: Hash2Vec
- Dimensionality Reduction Technicque: SVD
- Number of singular values used in SVD: 5
- Clustering Algorithm: Hierarchical Clustering
- Distance Metric: Cosine Similarity
- Linkage Method: Weighted