## How to Install MongoDB on Debian 11

### Introduction

MongoDB is a NoSQL database application used to store data as JSON-like documents on servers. MongoDB has modern infrastructure with various services while being malleable and friendly to use, providing freedom to developers and their code.

- Cross-Platform
- Optional Schemas
- Various Security and Encryption features
- Easy Implementation

### Prerequisites

- Deploy a Debian 11 instance.
- Login to the instance with a sudo user.

### Installing MongoDB

`sudo apt install gnupg2 wget`

Add the MongoDB public GPG key.

`wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -`

`echo "deb http://repo.mongodb.org/apt/debian buster/mongodb-org/5.0 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list`

`sudo apt update`

`sudo apt install mongodb-org`

#### Verify MongoDB was successfully installed.

```
mongod --version

db version v5.0.6
    Build Info: {
        "version": "5.0.6",
        "gitVersion": "212a8dbb47f07427dae194a9c75baec1d81d9259",
        "openSSLVersion": "OpenSSL 1.1.1k  25 Mar 2021",
        "modules": [],
        "allocator": "tcmalloc",
        "environment": {
        "distmod": "debian10",
        "distarch": "x86_64",
        "target_arch": "x86_64"
    }
}
```

#### Start the MongoDB service.

`sudo systemctl start mongod`

#### Enable MongoDB to start when the instance boots.

`sudo systemctl enable mongod`

## Creating a New User

Creating users in MongoDB's environment is simple and useful to authorize yourself in specific databases and access features within MongoDB.

`sudo mongosh`

`use admin`

use block add and substitute user and password as desired

```
db.createUser(
    {
        user: "admin",
        pwd:  "password",
        roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
    }
)
```

Successfully creating a new user, Mongosh prompts the following output.

`{ ok: 1 }`

`show users`

output

```
[
    {
        _id: 'admin.admin',
        userId: UUID("497f12fe-2142-4a3c-b846-fbc3bd9f711a"),
        user: 'admin',
        db: 'admin',
        roles: [ { role: 'userAdminAnyDatabase', db: 'admin' } ],
        mechanisms: [ 'SCRAM-SHA-1', 'SCRAM-SHA-256' ]
    }
 ]
 ```
 ### Enabling Database Authentication

 `sudo nvim /etc/mongod.conf`

 #### Paste this code block into the MongoDB configuration file to enable authentication.

 ```
 security:
 authorization: enabled
 ```

#### Save and exit the configuration file, then restart MongoDB.

`sudo systemctl restart mongod`

#### Enter Mongosh with your username and password.

`sudo mongosh -u admin -p password`

#### Successfully authenticating, Mongosh prompts the following output.

```
Current Mongosh Log ID: 61fff39bf56ab6dd6b893038
Connecting to: mongodb://127.0.0.1:27017/directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+1.1.9
Using MongoDB:          5.0.6
Using Mongosh:          1.1.9

For mongosh info see: https://docs.mongodb.com/mongodb-shell/
```

### Conclusion

In this guide, you have learned how to install, add users, authenticate, and use databases within MongoDB.




