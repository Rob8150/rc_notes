## Mongo express basics

## //path to config
`cd /usr/local/lib/node_modules/mongo-express`

must be root
config.js
exit root


## see also 

# to enable security on mogodb itself see

`https://github.com/Rob8150/rc_notes/blob/main/localMongo.md`


### Make sure mongo is running

`sudo systemctl start mongod`


`sudo systemctl stop mongod`

## Launch as mogo-express as admin

`mongo-express --admin --url mongodb://127.0.0.1:27017`


`sudo mongosh`


`sudo mongosh -u admin -p password`

```bash
 cd /usr/local/lib/node_modules/mongo-express
 mongo-express --admin --url mongodb://127.0.0.1:27017
 nvim mongo-express
 mv mongo-express mongo-express.md
 sudo systemctl start mongod
 mongo-express --admin --url mongodb://127.0.0.1:27017

