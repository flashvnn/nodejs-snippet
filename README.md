# nodejs-snippet
Nodejs snippets for development

## Static file extension

JSON  
```json
{"flac":true,"jpg":true,"jpeg":true,"png":true,"gif":true,"ico":true,"js":true,"mjs":true,"css":true,"txt":true,"xml":true,"woff":true,"woff2":true,"otf":true,"ttf":true,"eot":true,"svg":true,"zip":true,"rar":true,"pdf":true,"docx":true,"xlsx":true,"doc":true,"xls":true,"html":true,"htm":true,"appcache":true,"manifest":true,"map":true,"ogv":true,"ogg":true,"mp4":true,"mp3":true,"webp":true,"webm":true,"swf":true,"package":true,"json":true,"md":true,"m4v":true,"jsx":true,"heif":true,"heic":true,"ics":true}
```

JS  
```js
{ flac: true, jpg: true, jpeg: true, png: true, gif: true, ico: true, js: true, mjs: true, css: true, txt: true, xml: true, woff: true, woff2: true, otf: true, ttf: true, eot: true, svg: true, zip: true, rar: true, pdf: true, docx: true, xlsx: true, doc: true, xls: true, html: true, htm: true, appcache: true, manifest: true, map: true, ogv: true, ogg: true, mp4: true, mp3: true, webp: true, webm: true, swf: true, package: true, json: true, md: true, m4v: true, jsx: true, heif: true, heic: true, ics: true }
```

## Nodejs request With Retry
```js
function wait (timeout) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve()
    }, timeout);
  });
}

async function requestWithRetry (url) {
  const MAX_RETRIES = 10;
  for (let i = 0; i <= MAX_RETRIES; i++) {
    try {
      return await request(url);
    } catch (err) {
      const timeout = Math.pow(2, i);
      console.log('Waiting', timeout, 'ms');
      await wait(timeout);
      console.log('Retrying', err.message, i);
    }
  }
}
```


## Total.js push notification with pushbulled
```js
var headers = {
    'Access-Token': 'pushbullet token'
};

var push_data  = {
  "push": {
    "application_name": "GoldPrice",
    "body": "If you see this on your computer, Android-to-PC notifications are working!\n",
    "icon": "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",
    "title": "Mirroring test",
    "type": "mirror"
  },
  "type": "push"
};

U.request('https://api.pushbullet.com/v2/ephemerals', ['post', 'json'], push_data, function(err, data){
    console.log(err, data);
}, {}, headers);
```
