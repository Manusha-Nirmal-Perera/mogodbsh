<a name="top"></a>

# MongoDB + Doker Operations

## Table of Contents

1. [MongoDB Operations](#mongodb-operations)
   - [Insert Data](#insert-data)
     - [Insert a Single Document](#insert-a-single-document)
     - [Insert Multiple Documents](#insert-multiple-documents)
   - [Fetch and Display All Documents](#fetch-and-display-all-documents)
   - [Update Data](#update-data)
     - [Update the First Matching Document](#update-the-first-matching-document)
     - [Update All Matching Documents](#update-all-matching-documents)
   - [Replace Documents](#replace-documents)
   - [Delete Data](#delete-data)
6. [Setting Up a MongoDB Container with Docker](#setting-up-a-mongodb-container-with-docker)
   - [Check If Computer Port Is Busy](#check-if-computer-port-is-busy)
   - [List Available Images](#list-available-images)
   - [Pull MongoDB Image](#pull-mongodb-image)
   - [Remove an Unwanted Image](#remove-an-unwanted-image)
   - [Run MongoDB Container](#run-mongodb-container)
   - [Delete a Container](#delete-a-container)
   - [Access MongoDB Shell](#access-mongodb-shell)
   - [Login to MongoDB](#login-to-mongodb)
   - [Show All Databases](#show-all-databases)
   - [Switch to Database](#switch-to-database)
   - [Verify Current Database](#verify-current-database)
   - [Show Available Collections](#show-available-collections)

---

# MongoDB Operations

## Insert Data

### Insert a Single Document
```javascript
db.tableName.insertOne({ field1: value, field2: value })
```

### Insert Multiple Documents
```javascript
db.tableName.insertMany([
    { field1: value, field2: value },
    { field1: value, field2: value },
])
```

## Fetch and Display All Documents
```javascript
db.tableName.find().pretty()
```

## Update Data

### Update the First Matching Document
```javascript
db.tableName.updateOne(
    { targetField: value },  
    { $set: { field1: value, field2: value } }
)
```

### Update All Matching Documents
```javascript
db.tableName.updateMany(
  { targetField: value },
  { $set: { field1: value } }
)
```

## Replace Documents
```javascript
db.tableName.replaceOne(
    { targetField: "value" },  
    { field1: value, field2: value }
)
```

## Delete Data
```javascript
db.users.deleteOne({ targetField: "value" })
```

[⬆ Back to Top](#top)

# Setting Up a MongoDB Container with Docker

## Check If Computer Port Is Busy
```sh
netstat -ano | findstr :<host_port>
```

## List Available Images
```sh
docker images
```

## Pull MongoDB Image
Replace with required version:
```sh
docker pull mongo:<version>
```

## Remove an Unwanted Image
Replace `<image_id>` with the image ID of the required image:
```sh
docker rmi <image_id>
```

## Run MongoDB Container
```sh
docker run -d -p <host_port>:<container_port> --name <container_name> mongo:<version>
```

## Delete a Container
```sh
docker rm <container_id>
```

## Access MongoDB Shell
```sh
docker exec -it <container_id> mongosh
```
Replace `<container_id>` with the actual container ID, which can be found using:
```sh
docker ps
```

## Login to MongoDB

Start the container:
```sh
docker start <container_id>
```

Access the MongoDB shell:
```sh
docker exec -it <container_id> mongosh
```

## Show All Databases
```sh
show dbs
```

Authenticate:
```sh
use admin
db.auth("username", "password")
```
Replace `username` and `password` with your actual MongoDB credentials.

## Switch to Database
```sh
use <your_db_name>
```

## Verify Current Database
```sh
db
```

## Show Available Collections
```sh
show collections
```

[⬆ Back to Top](#top)
