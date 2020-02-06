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

<div style="width:100%;height:0;padding-bottom:54%;position:relative;"><iframe src="https://giphy.com/embed/LpkBAUDg53FI8xLmg1" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><p><a href="https://giphy.com/gifs/reaction-mood-LpkBAUDg53FI8xLmg1">via GIPHY</a></p>

Como gosto de usar o Jupyter Notebook vou usar a bibliteca [clojupyter](https://github.com/clojupyter/clojupyter).

[//]: # ([I'm a link](https://www.google.com))


```clojure
(require '[clojupyter.misc.helper :as helper])
(helper/add-dependencies '[incanter "1.5.7"])
(use '(incanter core stats charts io)) ; include Incanter's facilities into working namespace
```

```clojure
(-> (scatter-plot (sample-normal 1000)
                  (sample-normal 1000)
                  :x-label "x" :y-label "y")
    (.createBufferedImage 600 400))
```


{{< figure src="/a.png" title="Win" width="100%" >}}
