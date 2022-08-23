## Mongo with docker

#### docker

```bash
docker ps -a
docker start b9d502ef4174
docker start 01b750e131c0
```

#### mongo express

`localhost:8081`    

#### enter the docker container

```bash
docker container exec -it b9d502ef4174 /bin/bash
mongo admin -u admin -p password
```

#### latest

`mongosh admin -u admin -p password`

#### Show Databases

`show dbs`

#### Use Database db

`use db`

#### Show collection

`show collections`

#### find records

```bash
db.users.find()
db.users.find(ObjectId("6302ff024a715909fd4c66a9"))
```

#### clear the screen

`cls`

#### create database test

`use test`

#### [create a collection]

`db.createCollection("employee")`


#### [drop database]

`db.dropDatabase()`

#### [ drop employeee collection ]

`db.employeee.drop()`

#### [ insert record ]

`db.employee.insertOne({'first':'Suzzan','last':'Bowden', 'email':'bella.bowden.@example.com'})`

#### [ find one record ]

```bash
db.employee.findOne(ObjectId("6304570c21734e298cc0225a"))
db.employee.findOne({last:"bowden"})
db.employee.findOne()
db.employee.find()
```


