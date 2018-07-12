
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

