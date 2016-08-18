
MongoDB - Aula 01 - Exercício

autor: Adriel Cardoso dos Santos
Importando os restaurantes

mongoimport --db be-mean --collection restaurantes --drop --file restaurantes.json 
2016-08-18T12:29:19.318-0300	connected to: localhost
2016-08-18T12:29:19.318-0300	dropping: be-mean.restaurantes
2016-08-18T12:29:20.652-0300	imported 25359 documents

Contando os restaurantes

sydd(mongod-3.2.0-rc2-74-g78d3e85) test> use be-mean
switched to db be-mean
sydd(mongod-3.2.0-rc2-74-g78d3e85) be-mean> db.restaurantes.find({}).count();
25359


