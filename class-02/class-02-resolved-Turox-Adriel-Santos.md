# MongoDb - Aula 02 - Exercício
Autor: Igor Rotondo Bagliotti

## Criar database chamada be-mean-pokemons
		be-mean-pokemons> use be-mean-pokemons
		switched to db be-mean-pokemons

## Listagem de todas dbs

    be-mean-pokemons> show dbs;
		be-mean           → 0.004GB
		be-mean-instagram → 0.000GB
		be-mean-pokemons  → 0.000GB
		be-mean-teste     → 0.000GB
		local             → 0.000GB

  
## Listagem de todas as collections

    be-mean-pokemons> show collections
		pokemons → 0.001MB / 0.035MB
  
## Criar cinco pokemons

    be-mean-pokemons> db.pokemons.insert( [{"name": "Obesochu",   "description": "Raríssimo espécime",   "type": "otaku",   "attack": 2,   "height": 200 },{"name": "Onyx",   "description": "Grande pokemon de pedra no formato fálico",   "type": "preda",   "attack": 200,   "height": 50 }, {"name": "Ditto",   "description": "Pokemon que se transforma em outros",   "type": "agua",   "attack": 200,   "height": 50 }, {"name": "Ratata",   "description": "Pokemon mais poderoso de todos",   "type": "terra",   "attack": 10000,   "height": 15 },{"name": "Caterpie",   "description": "Larva lutadora",   "type": "Inseto",   "attack": 30,   "height": 0.3,   "defense": 35 } ]);
	Inserted 1 record(s) in 141ms
		BulkWriteResult({
  		"writeErrors": [ ],
  		"writeConcernErrors": [ ],
  		"nInserted": 5,
  		"nUpserted": 0,
  		"nMatched": 0,
  		"nModified": 0,
  		"nRemoved": 0,
  		"upserted": [ ]
	})

## Listar todos os pokemons

    be-mean-pokemons> db.pokemons.find()
			{
  			"_id": ObjectId("57b5dad09549e26e9269cd0f"),
  			"name": "Obesochu",
  			"description": "Raríssimo espécime",
  			"type": "otaku",
  			"attack": 2,
  			"height": 200
			}
			{
  			"_id": ObjectId("57b5dad09549e26e9269cd10"),
  			"name": "Onyx",
  			"description": "Grande pokemon de pedra no formato fálico",
  			"type": "preda",
  			"attack": 200,
  			"height": 50
			}
			{		
  			"_id": ObjectId("57b5dad09549e26e9269cd11"),
  			"name": "Ditto",
  			"description": "Pokemon que se transforma em outros",
  			"type": "agua",
  			"attack": 200,
  			"height": 50
			}
			{
  			"_id": ObjectId("57b5dad09549e26e9269cd12"),
  			"name": "Ratata",
  			"description": "Pokemon mais poderoso de todos",
  			"type": "terra",
				"attack": 10000,
  			"height": 15
			}
			{
  			"_id": ObjectId("57b5dad09549e26e9269cd13"),
  			"name": "Caterpie",
  			"description": "Larva lutadora",
  			"type": "Inseto",
  			attack": 30,
  			"height": 0.3,
  			"defense": 35
			}
			Fetched 5 record(s) in 7ms

  
## Buscar um pokemon

	
    be-mean-pokemons> var query = {name: 'Obesochu'};
		be-mean-pokemons> var poke =  db.pokemons.findOne(q)
		be-mean-pokemons> var poke =  db.pokemons.findOne(query);
		be-mean-pokemons> poke
			{
  			"_id": ObjectId("57b5dad09549e26e9269cd0f"),
  			"name": "Obesochu",
  			"description": "Raríssimo espécime",
  			"type": "otaku",
  			"attack": 2,
  			"height": 200
			}


  
## Editar a description do pokemon escolhido

    be-mean-pokemons> poke.description = "Hello";
		Hello
		db.pokemons.save(poke);
		Updated 1 existing record(s) in 3ms
		WriteResult({
  		"nMatched": 1,
  		"nUpserted": 0,
  		"nModified": 1
		})

