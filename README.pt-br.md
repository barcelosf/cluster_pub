# ClusterPub

ClusterPub é uma ferramenta desenvolvida para ajudar pesquisadores em seus processos de revisão bibliográfica, auxiliando-os a encontrar artigos relacionados às suas áreas de interesse, com base em resultados de busca retornados por repositórios de artigos, como IEEE Xplore e PubMed.

## Casos de Uso 📚

### Revisão Bibliográfica para TCC
Um aluno de graduação precisa fazer uma revisão bibliográfica sobre Inteligência Artificial para seu trabalho de conclusão de curso. Ele realiza uma busca no IEEE Xplore e exporta os resultados em formato BibTeX. Com centenas de artigos, o processo manual de filtragem e organização seria demorado.

Usando a ferramenta ClusterPub, ele processa o arquivo BibTeX em alguns segundos, gerando um dendrograma que agrupa os artigos com base em suas similaridades. Dessa forma, ele pode identificar rapidamente quais artigos são mais relevantes para seu tema de pesquisa, otimizando o tempo gasto na seleção dos materiais.

### Organização de Fontes em Pesquisa Colaborativa
Uma equipe de pesquisadores trabalhando em um projeto interdisciplinar (envolvendo saúde mental e neurociência) coleta artigos de diferentes repositórios, como IEEE Xplore e PubMed, exportando os arquivos em diferentes formatos (BibTeX e NBIB). Cada membro da equipe tem diferentes focos de interesse, e o número de artigos reunidos é muito grande para ser analisado manualmente.

A ferramenta ClusterPub é usada para agrupar automaticamente os artigos por similaridade temática. O resultado, exibido em forma de dendrograma, ajuda a equipe a identificar subgrupos de artigos e definir quais textos são prioritários para cada subárea, facilitando a divisão das leituras e a organização da pesquisa colaborativa.

## Linguagem de Programação 💻

ClusterPub foi desenvolvido utilizando Python 3.11.

## Instalação 🛠

É possível utilizar o ClusterPub como uma CLI independente, para isso instale-o com pip:

```bash
pip install cluster-pub
```

Mas se você quiser executar o código por conta própria, execute os seguintes comandos:

### Atualize os pacotes do Linux e instale dependências

Primeiro, atualize os pacotes do Linux e instale as dependências necessárias.

```bash
sudo apt update
sudo apt install -y python3-pip python3-dev
```

### Instale pipx e Poetry

Em seguida, instale pipx e Poetry.

```bash
python3 -m pip install --user pipx
python3 -m pipx ensurepath
pipx install poetry
```

### Instale o Python 3.11

Agora, instale o Python 3.11 usando a ferramenta `pyenv`. Caso não tenha o `pyenv` instalado, você pode instalá-lo com o seguinte comando:

```bash
curl https://pyenv.run | bash
```

Em seguida, instale o Python 3.11:

```bash
pyenv install 3.11.0
```

### Crie um ambiente virtual Python

Crie um novo ambiente virtual Python usando o Poetry.

```bash
poetry env use 3.11
poetry shell
```

### Instale as dependências do projeto

Por fim, instale as dependências do projeto usando o Poetry.

```bash
poetry install
```


## Executar o ClusterPub 🚀

Para executar o ClusterPub, execute o seguinte comando:

```bash
cluster-pub {source_file} {result_file}
```

Nota: O nome do result_file deve conter a extensão desejada.

## Extrair Métricas de Agrupamento 📈

OBS: O argumento number_of_clusters não especifica o número desejado de clusters, mas sim o número de clusters/categorias que pode haver no conjunto de dados analisado.

Para calcular métricas de agrupamento, como Índice de Silhueta, Índice de Davies-Bouldin e Índice de Calinski-Harabasz, execute os seguintes comandos:

```bash
cluster-pub-metrics davies-bouldin-score {source_file} {number_of_clusters}
cluster-pub-metrics calinski-harabasz-score {source_file} {number_of_clusters}
cluster-pub-metrics silhouette-score {source_file} {number_of_clusters} --distance-metric={distance_metric}
```

## Informações Básicas 🔍

Os hiperparâmetros e algoritmos padrão usados neste projeto são:

- Técnica de Word Embeddings: Hash2Vec
- Técnica de Redução de Dimensionalidade: SVD
- Número de valores singulares usados no SVD: 8
- Algoritmo de Agrupamento: Agrupamento Hierárquico
- Métrica de Distância: Similaridade dos Cossenos
- Método de Ligação: Média Ponderada das Distâncias
- Idiomas Suportados: Inglês
