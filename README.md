# qrcode-generator
QR Code Generator implementation in JavaScript.

A fork version of [kazuhikoarase/qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator),which contains Java and Ruby and some other language verisons.
This repo only support Javascript,based on this serve more friendly api.

To add this to project:

```javascript
const qrcode = require('qrcode-generator'); // CMD is the only support standard.
const qrMaker = qrcode(4,m,true);
``` 
As you can see, when we want to use apis we have to get a qrMaker object which contains servial methods.The qrcode has three prarms:

name | type | demo | note
:-:|:-:|:-:|:-:
TypeNumber | number | 4 | from 0 to 40
ErrorCorrectLevel | string | "M" | one of "L","M","H"
UTF-8 support | boolean | true | utf-8 support enable

all above are not necessary, default params are `(4,"M",false)`

##Apis
###addData
To add string you want to use for qrcode.( 70 max length limited )

###make
To make qrcode data info,use this method.

###getBase64Image
With this you could get base64 code for qrcode image.

Method above shoud be called Successively.

##Code demo
```javascript
const qrcode = require('qrcode-generator');
				,targteMessage = 'Give me five';
				,qrMaker = qrcode( 4, 'M', true)//				 
qrMaker.addData( targetMessage );
qrMaker.make();
var imageBase64String = qrMaker.getBase64Image();


```

I have hide servial api because this repo is determind to support react native.