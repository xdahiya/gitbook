# Types of ML

## based on supervision needed



<figure><img src="https://blogs.sas.com/content/subconsciousmusings/files/2017/09/styles-of-learning.jpg" alt=""><figcaption></figcaption></figure>



1. **supervised**

where we have both input and output like labeled data

1. regression        =>  numerical data output ex prediction of package / price of house /number of dog in a pic
2. classification  =>  categorical data output ex prdicition of placement mila ya nahi or package slab / spam mail / rain or not prediction /dog present or not in a pic

* **unsupervised**

were we have only input like iq and cgpc only not placement records

1. clustering      => classify and extract groups from data
2. dimenonsilty reduction   =>  reduce extra columns or mix&#x20;
3. anomolis detection => detecting outliears
4. association rule learning => detecting between associatioins

* **semi-sueprvisied**&#x20;

data is not completely labeled we only have some labeled data&#x20;

* **reinforcement**

no data learn forms his actions automatically



## based on training in production



<figure><img src="https://miro.medium.com/v2/resize:fit:1400/1*uTDNoo8Nrx0W5p66mOgzhw.png" alt=""><figcaption></figcaption></figure>

* batch learning

periodcally offline train model in batches with data freqently and then push to server frequently after test no incremental learning

* online learning

always train model in live with updating data&#x20;

incremental learning in little bunches of data freqently directly on server

like youtube recommedion changes in live time

_**advantages :-**_

need in concept drift&#x20;

cost effective

fast&#x20;



river python library and&#x20;

vowpal wabbit

tricky to use and risky sometimes



## based on how our model learn



<figure><img src="https://miro.medium.com/v2/resize:fit:1400/1*4PM3gvsdP9dJyAkenCeSIA.png" alt=""><figcaption></figcaption></figure>

* instance based learning

example like knn by checking the nearest neighbors

no training and learinign from data

* model based learning

in this use some mathamatics function or relationship to know about internal inputs and output

use trainig and after model no data points is required

learning are two types

memorising and generalising

instantance base learning remember the data but in model based learning the underline concept in learn and understand by the machine laerning algo&#x20;





