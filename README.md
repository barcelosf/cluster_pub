# ClusterPub

ClusterPub is a tool developed to help researchers in their processes of bibliographic review, 
helping them to find papers related to their areas of interest,
based on search results returned by paper repositories, like IEEE Xplore and Pubmed.

## Programming Language 💻

ClusterPub was developed using Python 3.11.

## Installation 🛠

It is possible to use ClusterPub as a standalone CLI, to do so install it with pip:

```bash Python installation command
pip install cluster-pub
```

But if you want to run the code by yourself, execute the following commands:

### Update Linux packages and install dependencies

First, update the Linux packages and install the necessary dependencies.

```bash
sudo apt update
sudo apt install -y python3-pip python3-dev
```

### Install pipx and Poetry

Next, install pipx and Poetry.

```bash
python3 -m pip install --user pipx
python3 -m pipx ensurepath
pipx install poetry
```

### Install Python 3.11

Now, install Python 3.11 using the `pyenv` tool. If you don't have `pyenv` installed, you can install it using the following command:

```bash
curl https://pyenv.run | bash
```

Then, install Python 3.11:

```bash
pyenv install 3.11.0
```

### Create a Python virtual environment

Create a new Python virtual environment using Poetry.

```bash
poetry env use 3.11
poetry shell
```

### Install project dependencies

Finally, install the project dependencies using Poetry.

```bash
poetry install
```

## Run ClusterPub 🚀

To execute ClusterPub, run the following command:

```bash
cluster-pub {source_file} {result_file}
```

Note: The result_file name should contain the desired extension.

## Extract Clustering Metrics  📈

OBS: The argument number_of_clusters does not specify the desired number of clusters, but it is the number of clusters/categories that might exit the analyzed dataset.

To calculate clustering metrics, like Silhouette Score, Davies-Bouldin Score, and Calinski-Harabasz Score, run the following commands:

```bash
cluster-pub-metrics davies-bouldin-score {source_file} {number_of_clusters}
cluster-pub-metrics calinski-harabasz-score {source_file} {number_of_clusters}
cluster-pub-metrics silhouette-score {source_file} {number_of_clusters} --distance-metric={distance_metric}
```

## Background Information 🔍

The default hyperparameters and algorithms used in this project are:

- Word Embeddings Technique: Hash2Vec
- Dimensionality Reduction Technique: SVD
- Number of singular values used in SVD: 5
- Clustering Algorithm: Hierarchical Clustering
- Distance Metric: Cosine Similarity
- Linkage Method: Weighted


