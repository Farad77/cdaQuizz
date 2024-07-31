# Correction du Questionnaire sur MongoDB

## Questions à choix unique (en français)

1. Quel est le concept de base de stockage de données dans MongoDB ?
   
   Réponse correcte : b) Document
   
   Explication : Dans MongoDB, les données sont stockées dans des documents, qui sont des ensembles de paires clé-valeur. Ces documents sont regroupés en collections, qui sont l'équivalent des tables dans les bases de données relationnelles.

2. Quelle commande MongoDB est utilisée pour insérer un nouveau document dans une collection ?
   
   Réponse correcte : b) db.collection.insertOne()
   
   Explication : La méthode `insertOne()` est utilisée pour insérer un nouveau document dans une collection MongoDB. Par exemple, `db.collection.insertOne({name: "John", age: 30})` insérerait un nouveau document dans la collection spécifiée.

## Questions ouvertes (en anglais)

1. Briefly explain the difference between embedding and referencing in MongoDB data modeling.

   Réponse modèle : 
   In MongoDB data modeling, embedding and referencing are two strategies for representing relationships between data.

   Embedding involves nesting related data within a single document. This approach is good for "contains" relationships and when the embedded data is always loaded with the parent document. It allows for faster reads as all the related data can be retrieved in a single query.

   Referencing, on the other hand, involves storing a reference (typically the _id field) to a document in another collection. This approach is useful when dealing with large amounts of data, when the related data is not always needed, or when the data is updated frequently. It allows for more flexibility but may require additional queries to retrieve the related data.

2. What is sharding in MongoDB and why is it important for large-scale applications?

   Réponse modèle:
   Sharding in MongoDB is a method for distributing data across multiple machines. It's MongoDB's approach to scaling horizontally, allowing it to support deployments with very large data sets and high throughput operations.

   In a sharded cluster, data is partitioned across multiple servers (shards), with each shard containing a subset of the data. This allows the database to grow beyond the limitations of a single server, both in terms of storage capacity and processing power.

   Sharding is important for large-scale applications because it allows:
   1. Increased data capacity: By distributing data across multiple machines, sharding allows MongoDB to store more data than can fit on a single machine.
   2. Improved performance: Sharding can improve the read and write performance by distributing the load across multiple servers.
   3. Increased availability: Even if one shard goes down, the other shards can continue to handle requests.

   By using sharding, large-scale applications can maintain high performance and availability as their data and load increase, making it a crucial feature for applications that need to scale beyond the capacity of a single server.

