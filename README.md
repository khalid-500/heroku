# heroku

### DEFINE THE PORT 
```javascript
process.env.PORT || 3000
```
### Procfile
- Create File Name ####Procfile####
- Insert Thes Text In IT ####web: node index.js####
## HEROKU RESOURSE
- applay Heroku Postgres 
## HEROKU SETTING
- Reveal Config Vars ###add any globel varible you added in application###

### HEROKU DEPLOY
- GO TO HEROKU AND CREATE NEW ACCOUT
- GO TO DEPLOY AND CONNECTED WITH GITHUB AND SELECT THE REBO //ANY MOODIFY WILL APPLAY DIRECTLY 
### SELECT THE BUTTON
- Wait for CI to pass before deploy
- Enaple Automatic Deploy
- Deploy Branch


### CONNECTION DATABASE HEROKU
```javascript
require('dotenv').config()
const { Sequelize } = require('sequelize');

//USE TO RUN THE DATABASE ON HEROKKU TO MAKE CONFIGRATION 
let sequelizeOptions =
    process.env.NODE_ENV === "production"
        ? {
            dialect: 'postgres',
            protocol: 'postgres',
            dialectOptions: {
                ssl :{require: true,rejectUnauthorized: false},
                native: true
            }
        } : {};


module.exports= new Sequelize(process.env.DATABASE_URL,sequelizeOptions) //'postgres://user:pass@example.com:5432/dbname' Example for postgres
```
