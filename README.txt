
[PROJET]

   -> vue init webpack client




   { --- Client --- }

      npm install
      npm run start

   



   { --- Server--- }
  
      npm init -f
      npm install --save nodemon eslint
      
      In the package.json :
        "scripts": {
    		"start": "./node_modules/nodemon/bin/nodemon.js src/app.js --exec 'npm run lint && node'",
    		"lint": "./node_modules/.bin/eslint **/*.js"
  	},
      
      node ./node_modules/eslint/bin/eslint.js --init 
      (use a popular style guide - Standard - JavaScript)

      Creer /src/app.js 
         console.log('Hello')

      npm start

      { Si tout est ok }
      
      npm install --save express body-parser cors morgan 
      npm start

      { Si tout est ok }

      Modifier le /src/app.js
          const express = require('express')
          const bodyParser = require('body-paser')
          const cors = require('cors')
          const morgan = require('morgan')

	 const app = express()
	 app.use(morgan('combine'))
	 app.use(bodyParser.json())
	 app.user(cors())

	 app.listen(process.env.PORT || 8081)



  Après, ajoutez dans le app.js : 
    app.get('/status', (req, res) => {
      res.send({
        message: 'hello world'
      })
    })
    et testez localhost:8081/status
    renvoie du json
    Télécharger le plugin Chrome : API Rest

    + Commit + Push

    COTE Client
    npm install --save axios
    
    On change le server pour obtenir renvoyer un email (Cote Server)

      app.post('/register', (req, res) => {
        res.send({
          message: `hello ${req.body.email} ! You'r registered`
        })
      })

    Cote Client on créer le routing, on créer un composant Api(), un service
    AuthenticationService et un composant Register sur lequel on appelle notre service

    Ensuite, Ajoutons la BDD
    http://docs.sequelizejs.com/manual/tutorial/models-definition.html
    
    COTE SERVER: 
    npm install --save sequelize sqlite3  (@3.1.8)
    importer, utiliser pour créer une configuration et un model
    SEQUELIZE : ORM

    V2 : 16"22