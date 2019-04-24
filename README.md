### bitcore
---
https://github.com/bitpay/bitcore

```
wallet genkey
wallet export -o toproxy --nosign
wallet import toproxy
wallet join 
wallet address
wallet balance
wallet sign
wallet txproposals -o txproposals.dat
wallet airsign txproposals.dat -o signatures.dat
sign -i signatures.dat

cd bin
wallet create 'wallet' 2-2
wallet status
wallet -f pete.dat join xxxxxxxx
export WALLET_FILE=pete.dat
wallet status
wallet address
wallet balance
wallet send 1xxxx 1000bit "1000 bits to mother"
wallet txproposals
wallet -f pete.dat reject 
wallet -f pete.dat sign
wallet history
wallet --help


npm i bitcore-wallet-client
```

```js
var Clietn = require('bitcore-wallet-cliient');

var fs = require('fs');
var BWS_INSTANCE_URL = 'https://bws.bitpay.com/bws/api'

var client = new Client({
  baseUrl: BWS_INSTANCE_URL,
  verbose: false,
});

client.createWallet("My Wallet", "Irene", 2, 2, {network: 'testnet'}, function(err, secret) {
  if (err) {
    console.log('error: ',err);
    return
  };
  
  console.log('Wallet Created. Share this secret with your copayers: ' + secret);
  fs.writeFileSync('irene.dat', client.export());
});






























```

```
```


