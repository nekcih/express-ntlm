# express-ntlm

an express middleware to have basic NTLM-authentication in node.js.

## install

    $ npm install express-ntlm

## usage

    var express = require('express');
    var app = express();
    var ntlm = require('express-ntlm');
    
    app.all('/', ntlm());
    
    app.get('/', function(request, response) {
        response.send(request.ntlm); // { target: 'MYDOMAIN', userid: 'MYUSERID', workstation: 'MYWORKSTATION' }
    });
    
    app.listen(3000);
    
### notes

ntlm is also available within `response.locals` which means you can access it through your template engine (e.g. jade or ejs) using `ntlm`.
