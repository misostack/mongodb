# MongoDB

## Fundamentals

### 1. How data is organized?

Data in MongoDB is stored as documents

Documents are stored in collections

> What is document?

- A way to organize and store data as a set of field-value pairs

```json
{
  "name": "MongoDB"
}
```

> What is collection?

- An organized store of documents in MongoDB, usually with common fields between documents

### What is MongoDB Atlas?

> Database as a service for MongoDB

> Clusters: A group of servers that stored your data

> Replica set : a few connected MongoDB instances are configured to store the same data

> Instance : a single machine locally/in cloud running a certain software ( MongoDB in this case)

> Single cluster in Atlas: automatically configured as a replica set

> Services: manage cluster creation, run & maintain, use service provider of your choices,

Atlas free tier: free cluster, 3-server replica set, 512MB storage, never expired

### 2. Importing, Exporting, and Querying Data

> JSON

So MongoDB will store data in BSON, and view data in JSON

Stored in BSON, Views in JSON

Binary JSON

- speed
- space
- flexibility
- data support: String, Number(Integer, Long, Float, ...), Boolean, Array, Date, Raw Binary
- machine readable only

**Import & Export Data**

> JSON

```bash
mongoimport
mongoexport
```

> BSON

```bash
# BSON
mongodump --uri "uri"
mongorestore --uri "uri" --drop dump
# JSON
mongoexport --uri "uri" --collection=yourcollection  --out=filename.json
mongoimport --uri "uri" --drop filename.json


mongodump --uri "mongodb+srv://<your username>:<your password>@<your cluster>.mongodb.net/sample_supplies"

mongoexport --uri="mongodb+srv://<your username>:<your password>@<your cluster>.mongodb.net/sample_supplies" --collection=sales --out=sales.json

mongorestore --uri "mongodb+srv://<your username>:<your password>@<your cluster>.mongodb.net/sample_supplies"  --drop dump

mongoimport --uri="mongodb+srv://<your username>:<your password>@<your cluster>.mongodb.net/sample_supplies" --drop sales.json
```

> mongodb+srv://username:password@clusterURI.mongodb.net/database

SRV connection string - a specific format used to establish a connection between your application and a MongoDB instance

- [Connection string](https://www.mongodb.com/docs/manual/reference/connection-string/#connections-dns-seedlist)

## Learning Center

- https://university.mongodb.com/mercury/M001/2022_May_10/chapter/Chapter_2_Importing_Exporting_and_Querying_Data/lesson/5f35955a04e9ff7f1566edbb/lecture
