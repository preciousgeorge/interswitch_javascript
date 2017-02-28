```js
var Interswitch = require('interswitch')
var clientId = ""; // Get your Client ID from https://developer.interswitchng.com
var secret = ""; // Get your Client Secret from https://developer.interswitchng.com
var ENV = "SANDBOX"; // or PRODUCTION
var interswitch = new Interswitch(clientId, secret, ENV);

##sample payment request
var id = getUniqueId();
    var paymentReqRef = "ISW-SDK-PAYMENT-" + id;
    var req = { "transactionRef": paymentReqRef , "authData": authData };
    //console.log("\nValidate Req: " + req);
    var obj = {
        url: "api/v2/purchases/validations",
        method: "POST",
        requestData: req,
        httpHeaders: {"Content-Type": "application/json"}
    };

    //send the actual request
    interswitch.send(obj,function(err, response, body){
        if(err) {
            //error/exception occured
        }else {
            //success
            console.log(JSON.stringify(response));
        }
    });

```

## Installation

```bash
$ npm install interswitch
```

## Features

  * Sends request to Interswitch API
  * Calculates Interswitch Security Header
  * Packages Interswitch Sensitive Data (Card, PIN, CVV, Exp Date)
  * Generates PIN Block for Interswitch transactions
  * Generate MAC for Interswitch transactions
  
