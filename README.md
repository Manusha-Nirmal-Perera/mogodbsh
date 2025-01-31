# MongoDB Operations

## Insert Data

### Insert a Single Document
  ```javascript
    db.tableName.insertOne({ feild1: value, feild2: value })
  ```

### Insert a Multiple Documents
  ```javascript
    db.tableName.insertMany([
        { feild1: value, feild2: value },
        { feild1: value, feild2: value },
    ])
  ```

## Fetch and display all documents in a formatted way
  ```javascript
      db.tableName.find().pretty()
  ```

## Update data

### Updates the first matching document
  ```javascript
    db.tableName.updateOne(
        { targetFeild: value },  
        { $set: { feild1: value, feild2: value } }
    )               
  ```
  
### Updates all documents found with target feilds
  ```javascript
    db.tableName.updateMany(
      { targetFeild: value },
      { $set: { feild1: value } }
    )
  ```

## Repalce documents
  ```javascript
    db.tableName.replaceOne(
        { targetFeild: "value" },  
        { feild1: value, feild2: value }
    )
  ```

## Delete data
  ```javascript
    db.users.deleteOne({ targetFeild: "value" })
  ```
