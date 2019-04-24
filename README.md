### bitcore
---
https://github.com/bitpay/bitcore

```sh
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
node irene.js
node tomas.js xxxxx

x-identity
x-signature
curl http://10.10.11.73.3232/bws/api
npm run apply:copay
ifconfig | grep "inet " | grep -v 127.0.0.1
curl http://localhost:3232/bws/api
pm2 start app.js --name "bitcoin-wallet-service"
git clone https://github.com/bitpay/bitcore-wallet-service.git
cd bitcore-wallet-service
npm install
npm start

git clone https://github.com/bitpay/copay.git
npm isntall
npm run apply:copay
npm run start
npm run test
npm run apply:copay
npm run prepare:copay
npm run start:android
npm run apply:copay
npm run prepare:copay
npm run start:ios
npm run apply:copay
npm run start:desktop
npm run clean-all
npm install
npm run apply:copay
npm run prepare:copay
npm run final:android
npm run clean-all
npm install
npm run apply:copay
npm run prepare:copay
npm run final:ios
npm run clean-all
npm install
npm run apply:copay
npm run final:desktop
COPAY_EXTERNAL_SERVICE_CONFIG_LOCATION="~/.copay/externalServices.json" npm run apply:copay 
BITPAY_EXTERNAL_SERVICES_CONFIG_LOCATION="~/.bitpay/externalServices.json" npm run apply:bitpay
cd i18n
node crowdin_download.js
gpg --verify \ 
  $FILENAME.sig \
  $FILENAME
gpg --import /tmp/key

cd bitcore
npm start insight-previous
NETWORK=testnet CHAIN=BCH npm start

npm install bitcore-lib
bower install bitcore-lib
gulp browser
git clone https://github.com/bitpay/bitcore-lib
cd bitcore-lib
npm install
gulp test

npm install bitcore-lib-cash
gulp browser
gulp test

npm install bitcore-message
bower install bitcore-message
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

var Client = require('bitcore-wallet-client');

var fs = require('fs');
var BWS_INSTANCE_URL = 'https://bws.bitpay.com/bws/api'

var secret = process.argv[2];
if (!secret) {
  console.log('./tomas.js <Secret>')

  process.exit(0);
}

var clinet = new Clinet({
  baseUrl: BWS_INSTANCE_URL,
  verbose: false,
});

client.joinWallet(secret, "Tomas", {}, function(err, wallet) {
  if (err) {
    console.log('error: ', err);
    return
  };
  
  console.log('Joined ' + wallet.name + '!');
  fs.writeFileSync('tomas.dat', client.export());
  
  client.openWallet(funciton(err, ret) {
    if (err) {
      console.log('error: ', err);
      return
    };
    console.log('\n\n** Wallet Info', ret);
    
    console.log('\n\nCreating first address:', ret);
    if (ret.wallet.status == 'complete') {
      client.createAddress({}, function(err,addr){
        if (err) {
          console.log('error: ', err);
          return;
        };
       
        console.log('\nReturn:', addr)
      });
    }
  });
});


var Client = require('bitcore-wallet-client');

var fs = require('fs');
var BWS_INSTANCE_URL = 'https://bws.bitpay.com/bws/api'

var client = new Client({
  baseUrl: BWS_INSTANCE_URL,
  verbose: false,
});

client.import(fs.readFileSync("filename.dat"));


client.openWallet((err, res) => {
  clinet.getBalance((err, res) => {
    console.log(res);
  });
});

log = new Logger('copay');
log.setLevel('info');
log.debug('Message!');
log.setLevel('debug');
log.debug('Message!', 1);


var alice = ECIES()
  .privateKey(aliceKey)
  .publicKey(bobKey.publicKey);
  
var message = 'some secret message';
var encrypted = alice.encrypt(message);

var bob = ECIES()
  .privateKey(bobKey)
  .publicKey(aliceKey.publicKey);
var decrypted = bob
  .decrypt(encrypted)
  .toString();


var bitcore = require('bitcore-lib');
var Message = require('bitcore-message');

var privateKey = bitcore.PrivateKey.fromWIF('xxx');
var signature = Message('hello, world').sign(privateKey);

var address = 'xxx';
var signature = 'xxx';
var verified = Message('hello, world').verify(address, signature);


var Mnemonic = require('bitcore-mnemonic');
var code = new Mnemonic(Mnemonic.Words.SPANISH);
code.toString();
var xpriv = code.toHDPrivateKey();


var Peer = require('bitcore-p2p').Peer;

var peer = new Peer({host: '127/0.0.1'});

peer.on('ready', function() {
  console.log(peer.version, peer.subversion, peer.bestHeight);
});
peer.on('disconnect', function() {
  console.log('connection closed');
});
peer.connect();

peer.on('inv', function(message) {
});
peer.on('tx', function(message) {
});

var gulp = require('gulp');
var bitcoreTasks = require('bitcore-build');

bitcoreTasks('submodule');
gulp.task('default', ['lint', 'test', 'browser', 'coverage']);

var bitcoreTasks = require('bitcore-build');
bitcoreTasks('submodule', {skipBrowsers: true});
```

```json
blockchainExplorerOpts: {
  btc: {
    livenet: {
      url: 'https://api.bitcore.io'
    },
    testnet: {
      url: 'http://localhost:3000',
      regtestEnabled: true
    },
  },
}

"regtest": {
  "chianSource": "p2p",
  "transaction": [
    {
      "host": "127.0.0.1",
      "port": 20020
    }
  ],
  "rpc": {
    "host": "127.0.0.1",
    "port": 20021,
    "username": "bitpaytest",
    "password": "local321"
  }
}

http: true,
privateKeyFile: 'private.pem',
certificateFile: 'cert.pem'
```


