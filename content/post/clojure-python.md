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

O Clojure por outro lado não possui a mesma tradição nesta área, apesar disso temos várias bibliotecas que podem ser utilizadas como: [Incanter](https://github.com/incanter/incanter), entre outras exposta no [Scicloj](https://scicloj.github.io/). Porém é interessante aprender o paradigma funcional para tentarmos deixar o nosso código em Python com menos [efeitos colaterais](http://pythonclub.com.br/progrmacao-funcional-com-python-1.html).

Além disso o com o Clojure temos acesso a máquina virtual Java (JVM). Ou seja, podemos
acessar aplicativos escritos em Java, como: Hadoop, Spark e Hive. Por exemplo temos
as bibliotecas [Sparkling](https://gorillalabs.github.io/sparkling/) para Spark e para Hadoop temos [Cascalog](https://github.com/nathanmarz/cascalog).

## Apresentando libpython-clj e panthera

Procurei mais detalhes sobre como poderia unir estas duas liguagens maravilhosas e acabei tropeçando em duas bibliotecas incríveis, uma delas é a [libpython-clj](https://github.com/cnuernber/libpython-clj) que coloca o Python "dentro" do Clojure e conseguimos então fazer chamadas
em métodos e compartilhar dados entre elas.

Outra é a [panthera](https://github.com/alanmarazzi/panthera) que une o trabalho anterior
com a famosa biblioteca Pandas do Python para ingestão e manipulação de dados tabulares.

[//]: # ([I'm a link](https://www.google.com))
