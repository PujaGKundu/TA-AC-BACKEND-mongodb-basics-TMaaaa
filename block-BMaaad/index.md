writeCode

Write command to

- List collections from a database.
  > show dbs
  > admin 0.000GB
  > config 0.000GB
  > local 0.000GB
  > mylib 0.000GB
- create a new collection in your country database which you created recently.
  > use India
  > switched to db India
  > db.createCollection("capital")
  > { "ok" : 1 }

Write code to:-

- crate a database named `weather`
  > use weather
- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.
  > db.createCollection( "temprature", { capped: true, size: 100000 } )
- create a simple collection named `humidity`
  > db.createCollection("humidity")
- check whether `temperature` collection is capped or not ?
  > db.temprature.stats()
  > {
          "ns" : "weather.temprature",
          "size" : 0,
          "count" : 0,
          "storageSize" : 4096,
          "freeStorageSize" : 0,
          "capped" : true,
          "max" : 0,
          "maxSize" : 1000192,
          "wiredTiger" : {
                  "metadata" : {
                          "formatVersion" : 1
                  },
                  ........}
          }
- Delete `humidity` collection and then the entire database(weather).
  > db.humidity.remove({})
  > WriteResult({ "nRemoved" : 0 })
  > db.weather.drop()
  > true
