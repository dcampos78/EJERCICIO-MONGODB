***Consultas / Buscar documentos**

1.	***Obtener todos los documentos***
Cinema> db.Movies.find()
![Alt text](/EJERCICIO%20MONGODB/images/image1.1.png)

2.	***Obtener documentos con writer igual a "Quentin Tarantino"***
 db.Movies.find({writer: "Quentin Tarantino"})
![Alt text](/EJERCICIO%20MONGODB/images/image1.2.png)

3.	***Obtener documentos con actors que incluyan a "Brad Pitt"***
db.Movies.find({actors: "Brad Pitt"})
![Alt text](/EJERCICIO%20MONGODB/images/image1.3.png)

4.	***Obtener documentos con franchise igual a "The Hobbit"***
db.Movies.find({franchise: "The Hobbit"})
![Alt text](/EJERCICIO%20MONGODB/images/image1.4.png)

5.	***Obtener todas las películas de los 90s.***
db.Movies.find({year:{$lte: 1999}})
![Alt text](/EJERCICIO%20MONGODB/images/image1.5.png)

6.	***Obtener las películas estrenadas entre el año 2000 y 2010.***
db.Movies.find( { year: { $gte : 2000 , $lte : 2010} })
![Alt text](/EJERCICIO%20MONGODB/images/image1.6.png)


**Actualizar Documentos**

1.	***Agregar sinopsis a "The Hobbit: An Unexpected Journey" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."***
db.Movies.updateOne({title: "The Hobbit: An Unexpected Journey"},{$set: {sinopsis: "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug." }})
![Alt text](/EJERCICIO%20MONGODB/images/image2.1.png)

2.	***Agregar sinopsis a "The Hobbit: The Desolation of Smaug" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring***
db.Movies.updateOne({title: "The Hobbit: The Desolation of Smaug" },{$set: {sinopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring"}})
![Alt text](/EJERCICIO%20MONGODB/images/image2.2.png)


**Búsqueda por Texto / Text Search**

1. ***Encontrar las películas que en el título contengan la palabra "Hobbit"***
db.Movies.find({title : {$regex : "Hobbit"}});
![Alt text](/EJERCICIO%20MONGODB/images/image3.1.png)

2. ***Encontrar las películas que en la sinopsis contengan la palabra "Gandalf"***
db.Movies.find({sinopsis : {$regex : "Gandalf"}});
![Alt text](/EJERCICIO%20MONGODB/images/image3.2.png)

3. ***Encontrar las películas que en la sinopsis contengan la palabra "Bilbo" y no la palabra "Gandalf"***
db.Movies.find({sinopsis : {$regex : "Bilbo",$not: {$regex: "Gandalf"}}});
![Alt text]/EJERCICIO%20MONGODB/images/(image3.3.png)

4. ***Encontrar las películas que en la sinopsis contengan la palabra "dwarves" ó "hobbit"***
db.Movies.find({$or: [{sinopsis: {$regex: "dwarves"}}, {sinopsis: {$regex: "hobbit"}}]})
![Alt text](/EJERCICIO%20MONGODB/images/image3.4.png)

5. ***Encontrar las películas que en la sinopsis contengan la palabra "gold" y "dragon"***
db.Movies.find({$and: [{sinopsis: {$regex: "gold"}}, {sinopsis: {$regex: "dragon"}}]})
![Alt text](/EJERCICIO%20MONGODB/images/image3.5.png)


**Eliminar Documentos**

1.	***Eliminar la película "Pee Wee Herman's Big Adventure"*** 
db.Movies.deleteOne({title: "Pee Wee Herman's Big Adventure"})
![Alt text](/EJERCICIO%20MONGODB/images/image4.1.png)

2. ***Eliminar la película "Avatar"***
db.Movies.deleteOne({title: "Avatar"})
![Alt text](/EJERCICIO%20MONGODB/images/image4.2.png)


**Resultado Final Base de Datos**
![Alt text](/EJERCICIO%20MONGODB/images/imagefinal.png)


