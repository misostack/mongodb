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

## Quiz

```json
{
  "_id": ObjectId("5c9be463f752ec6b191c3c7e"),
  "item_code": "AS45OPD",
  "name": "Recycled Kicks",
  "maker_brand": "Shoes From The Gutter",
  "price": 100.00,
  "description": "These amazing Kicks are made from recycled plastics and
  fabrics.They come in a variety of sizes and are completely unisex in design.
  If your feet don't like them within the first 30 days, we'll return your
  money no questions asked.
  ",
  "materials": [
    "recycled cotton",
    "recycled plastic",
    "recycled food waste",
  ],
  "country": "Russia",
  "image": "https:///www.shoesfromthegutter.com/kicks/AS45OPD.img",
  "available_sizes": {
      "mens": ["5", "6", "8", "8W", "10", "10W", "11", "11W", "12", "12W"],
      "womens": ["5", "6", "7", "8", "9", "10", "11", "12"]
  },
  "package_weight_kg": 2.00,
  "average_rating": 4.8,
  "reviews": [{
      "author": "i_love_kicks",
      "text": "best shoes ever! comfortable, awesome colors and design!",
      "rating": 5
    },
    {
      "author": "i_know_everything",
      "text": "These shoes are no good because I ordered the wrong size.",
      "rating": 1
    },
    "..."
  ],
  "questions": [{
      "author": "i_love_kicks",
      "text": "Do you guys make baby shoes?",
      "likes": 1223
    },
    {
      "author": "i_know_everything",
      "text": "Why do you make shoes out of garbage?",
      "likes": 0
    },
    "..."
  ],
  "stock_amount": 10000,
  "maker_address": {
    "building_number": 7,
    "street_name": "Turku",
    "city": "Saint-Petersburg",
    "country": "RU",
    "postal_code": 172091
  },
  "makers": ["Ilya Muromets", "Alyosha Popovich", "Ivan Grozniy", "Chelovek Molekula"],
}
// building
{
  "_id": ObjectId("5c9414f25e6aff2b8870a2d0"),
  "address": {
    "building number": "742",
    "street name": "Evergreen Terrace",
    "city": "Springfield",
    "state": "MA",
    "zip code": "01111"
  },
  "owner": "Homer J. Simpson",
  "zone": 13,
  "date": ISODate("2019-03-21T23:03:31.197Z"),
  "kW per day": {
    "consumption": 10,
    "self-produced": 7,
    "city-supplemented": 3
  }
}
// zone
{
  "_id": "<objectId>",
  "zone": "<int>",
  "date": "<date>",
  "kW per day": {
    "consumption": "<int>",
    "self-produced": "<int>",
    "city-supplemented": "<int>"
  }
}

```
