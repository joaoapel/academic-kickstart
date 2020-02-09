---
title: "Clojure + Python"
date: 2020-02-05T16:41:34-03:00
draft: false
tags: ["clojure", "python", "data science"]
---

## Porque ?

O Python junto com R são as linguagens de programação mais utilizadas no mundo da
análise de dados. E possum milhares de bibliotecas que facilitam muito a vida do
analista.

O Clojure por outro lado não possui a mesma tradição nesta área, apesar disso temos várias bibliotecas que podem ser utilizadas como: [incanter](https://github.com/incanter/incanter), entre outras exposta no [Scicloj](https://scicloj.github.io/). Porém é interessante aprender o paradigma funcional para tentarmos deixar o nosso código em Python com menos [efeitos colaterais](http://pythonclub.com.br/progrmacao-funcional-com-python-1.html).

Além disso com o Clojure temos acesso a máquina virtual Java (JVM). Ou seja, podemos
interagir com aplicativos escritos em Java, como: Hadoop, Spark e Hive. Por exemplo temos
as bibliotecas [sparkling](https://gorillalabs.github.io/sparkling/) para Spark e para Hadoop temos [cascalog](https://github.com/nathanmarz/cascalog).

## Apresentando libpython-clj e panthera

Procurei mais detalhes sobre como poderia unir estas duas liguagens maravilhosas e acabei tropeçando em duas bibliotecas incríveis, uma delas é a [libpython-clj](https://github.com/cnuernber/libpython-clj) que coloca o Python "dentro" do Clojure e conseguimos então fazer chamadas
em métodos e compartilhar dados entre elas.

Outra é a [panthera](https://github.com/alanmarazzi/panthera) que une o trabalho anterior
com a famosa biblioteca Pandas do Python para ingestão e manipulação de dados tabulares.

## Como ?

<div style="width:100%;height:0;padding-bottom:54%;position:relative;"><iframe src="https://giphy.com/embed/LpkBAUDg53FI8xLmg1" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><p><a href="https://giphy.com/gifs/reaction-mood-LpkBAUDg53FI8xLmg1"></a></p>

Para criar a estrutura do projeto vou utilizar o pacote
do Python que se chama [cookiecutter](https://drivendata.github.io/cookiecutter-data-science/) para padronizar como os dados e scripts serão distribuídos.

```sh
├── LICENSE
├── Makefile           <- Makefile with commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default Sphinx project; see sphinx-doc.org for details
│
├── models             <- Trained and serialized models, model predictions, or model      
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creators initials, and a short `-` delimiteddescription,e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.py           <- Make this project pip installable with `pip install -e`
├── src                <- Source code for use in this project.
│   ├── __init__.py    <- Makes src a Python module
│   │
│   ├── data           <- Scripts to download or generate data
│   │   └── make_dataset.py
│   │
│   ├── features       <- Scripts to turn raw data into features for modeling
│   │   └── build_features.py
│   │
│   ├── models         <- Scripts to train models and then use trained models to make
│   │   │                 predictions
│   │   ├── predict_model.py
│   │   └── train_model.py
│   │
│   └── visualization  <- Scripts to create exploratory and results oriented visualizations
│       └── visualize.py
│
└── tox.ini            <- tox file with settings for running tox; see tox.testrun.org
```


Como gosto de usar o Jupyter Notebook vou usar a bibliteca [clojupyter](https://github.com/clojupyter/clojupyter).

[//]: # ([I'm a link](https://www.google.com))


```clojure
(require '[clojupyter.misc.helper :as helper])
(helper/add-dependencies '[incanter "1.5.7"])
(use '(incanter core stats charts io))
```

```clojure
(-> (scatter-plot (sample-normal 1000)
                  (sample-normal 1000)
                  :x-label "x" :y-label "y")
    (.createBufferedImage 600 400))
```
{{<figure src="/img/a.png" width="100%">}}
