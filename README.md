# api documentation for  [twitter-stream-channels (v1.0.0)](http://labs.topheman.com/twitter-stream-channels/)  [![npm package](https://img.shields.io/npm/v/npmdoc-twitter-stream-channels.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-twitter-stream-channels) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-twitter-stream-channels.svg)](https://travis-ci.org/npmdoc/node-npmdoc-twitter-stream-channels)
#### Manage multiple filters on the same Twitter stream

[![NPM](https://nodei.co/npm/twitter-stream-channels.png?downloads=true)](https://www.npmjs.com/package/twitter-stream-channels)

[![apidoc](https://npmdoc.github.io/node-npmdoc-twitter-stream-channels/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-twitter-stream-channels_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-twitter-stream-channels/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-twitter-stream-channels/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-twitter-stream-channels/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Christophe Rosset"
    },
    "bugs": {
        "url": "https://github.com/topheman/twitter-stream-channels/issues"
    },
    "dependencies": {
        "twit": "^2.1.0"
    },
    "description": "Manage multiple filters on the same Twitter stream",
    "devDependencies": {
        "jasmine-node": "^1.14.5",
        "yuidocjs": "^0.9.0"
    },
    "directories": {},
    "dist": {
        "shasum": "e5e9388aec9bf72254e2fe86930c301f7f0d74eb",
        "tarball": "https://registry.npmjs.org/twitter-stream-channels/-/twitter-stream-channels-1.0.0.tgz"
    },
    "gitHead": "4f740aeddd6ca2cc2492f9783addd3ad771bce46",
    "homepage": "http://labs.topheman.com/twitter-stream-channels/",
    "keywords": [
        "twitter",
        "api",
        "stream",
        "filter"
    ],
    "license": "MIT",
    "main": "./lib/TwitterStreamChannels",
    "maintainers": [
        {
            "name": "topheman",
            "email": "tophe@topheman.com"
        }
    ],
    "name": "twitter-stream-channels",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/topheman/twitter-stream-channels.git"
    },
    "scripts": {
        "test": "jasmine-node spec/offline --verbose --config highSpeed true",
        "test-online": "jasmine-node spec/online --verbose",
        "test-watch": "jasmine-node spec/offline --autotest --config highSpeed true --watch .",
        "yuidoc": "yuidoc"
    },
    "version": "1.0.0",
    "yuidoc": {
        "options": {
            "linkNatives": "true",
            "attributesEmit": "false",
            "selleck": "false",
            "paths": [
                "./lib",
                "./mocks"
            ],
            "outdir": "./yuidoc",
            "themedir": "./extras/yuidoc-theme-topheman"
        }
    }
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module twitter-stream-channels](#apidoc.module.twitter-stream-channels)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.</span>StreamChannels (apiClient, options)](#apidoc.element.twitter-stream-channels.StreamChannels)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.</span>getMockedClass ()](#apidoc.element.twitter-stream-channels.getMockedClass)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.</span>launchMockDataRetriever (credentials, options)](#apidoc.element.twitter-stream-channels.launchMockDataRetriever)
1.  object <span class="apidocSignatureSpan">twitter-stream-channels.</span>StreamChannels.prototype

#### [module twitter-stream-channels.StreamChannels](#apidoc.module.twitter-stream-channels.StreamChannels)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.</span>StreamChannels (apiClient, options)](#apidoc.element.twitter-stream-channels.StreamChannels.StreamChannels)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.</span>super_ ()](#apidoc.element.twitter-stream-channels.StreamChannels.super_)

#### [module twitter-stream-channels.StreamChannels.prototype](#apidoc.module.twitter-stream-channels.StreamChannels.prototype)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>_getOptionsToPassToApiClient (options)](#apidoc.element.twitter-stream-channels.StreamChannels.prototype._getOptionsToPassToApiClient)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>getChannels ()](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.getChannels)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>getChannelsKeywordsLowerCasedRegExp ()](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.getChannelsKeywordsLowerCasedRegExp)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>getTrackedKeywords ()](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.getTrackedKeywords)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>start ()](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.start)
1.  [function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>stop (options)](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.stop)



# <a name="apidoc.module.twitter-stream-channels"></a>[module twitter-stream-channels](#apidoc.module.twitter-stream-channels)

#### <a name="apidoc.element.twitter-stream-channels.StreamChannels"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.</span>StreamChannels (apiClient, options)](#apidoc.element.twitter-stream-channels.StreamChannels)
- description and source-code
```javascript
StreamChannels = function (apiClient, options) {
  helpers.checkStreamChannelsOptions(options, this);
  options.enableChannelsEvents = typeof options.enableChannelsEvents === 'undefined' ? true : options.enableChannelsEvents;
  options.enableRootChannelsEvent = typeof options.enableRootChannelsEvent === 'undefined' ? true : options.enableRootChannelsEvent
;
  options.enableKeywordsEvents = typeof options.enableKeywordsEvents === 'undefined' ? false : options.enableKeywordsEvents;
  helpers.preprocessKeywords(options, this);
  this.currentStream = apiClient.stream('statuses/filter',this._getOptionsToPassToApiClient(options));
  EventEmitter.call(this);
  addEvents(this.currentStream, this);
  this.options = options;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.twitter-stream-channels.getMockedClass"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.</span>getMockedClass ()](#apidoc.element.twitter-stream-channels.getMockedClass)
- description and source-code
```javascript
getMockedClass = function (){
  return require('../mocks/TwitterStreamChannels');
}
```
- example usage
```shell
...
	timeout:50000
});
'''

And then, you can use it like :

'''js
var TwitterStreamChannelsMocked = require('twitter-stream-channels').getMockedClass();
var client = new TwitterStreamChannelsMocked({
	tweets: require('./save/your/tweets.json'),
	singleRun: false //so that you loop on your mocked tweets unless you call .stop() (if put at true, emulates a disconnection from
 twitter)
});
// ... and then you can code like the example above (without connecting to twitter)
'''
...
```

#### <a name="apidoc.element.twitter-stream-channels.launchMockDataRetriever"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.</span>launchMockDataRetriever (credentials, options)](#apidoc.element.twitter-stream-channels.launchMockDataRetriever)
- description and source-code
```javascript
launchMockDataRetriever = function (credentials, options){
  return new require('./MockDataRetriever')(credentials,options);
}
```
- example usage
```shell
...

There are also examples in the repo, and the API is not that complicated ... But something that you could enjoy is the mocked version
 of the module that **allows you to code without needing to connect to Twitter**, since it has some connection limits over every
 15 minutes (those limits are not greatly specified for the streaming API).

With this simple code, you retrieve your fake data (see also [example](./examples/online/retrieveMockTweets.js "example")) :

'''js
var credentials = require('./twitter.credentials.json');
require('twitter-stream-channels').launchMockDataRetriever(credentials,{
	output: "./save/your/tweets.json",
	track:['blue','white','yellow','green','orange','kiwi','apple','lemon','coconut','Luke','Leia','Han','Yoda'],
	maxNumber:200,
	timeout:50000
});
'''
...
```



# <a name="apidoc.module.twitter-stream-channels.StreamChannels"></a>[module twitter-stream-channels.StreamChannels](#apidoc.module.twitter-stream-channels.StreamChannels)

#### <a name="apidoc.element.twitter-stream-channels.StreamChannels.StreamChannels"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.</span>StreamChannels (apiClient, options)](#apidoc.element.twitter-stream-channels.StreamChannels.StreamChannels)
- description and source-code
```javascript
StreamChannels = function (apiClient, options) {
  helpers.checkStreamChannelsOptions(options, this);
  options.enableChannelsEvents = typeof options.enableChannelsEvents === 'undefined' ? true : options.enableChannelsEvents;
  options.enableRootChannelsEvent = typeof options.enableRootChannelsEvent === 'undefined' ? true : options.enableRootChannelsEvent
;
  options.enableKeywordsEvents = typeof options.enableKeywordsEvents === 'undefined' ? false : options.enableKeywordsEvents;
  helpers.preprocessKeywords(options, this);
  this.currentStream = apiClient.stream('statuses/filter',this._getOptionsToPassToApiClient(options));
  EventEmitter.call(this);
  addEvents(this.currentStream, this);
  this.options = options;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.twitter-stream-channels.StreamChannels.super_"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.</span>super_ ()](#apidoc.element.twitter-stream-channels.StreamChannels.super_)
- description and source-code
```javascript
function EventEmitter() {
  EventEmitter.init.call(this);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.twitter-stream-channels.StreamChannels.prototype"></a>[module twitter-stream-channels.StreamChannels.prototype](#apidoc.module.twitter-stream-channels.StreamChannels.prototype)

#### <a name="apidoc.element.twitter-stream-channels.StreamChannels.prototype._getOptionsToPassToApiClient"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>_getOptionsToPassToApiClient (options)](#apidoc.element.twitter-stream-channels.StreamChannels.prototype._getOptionsToPassToApiClient)
- description and source-code
```javascript
_getOptionsToPassToApiClient = function (options){
  var result = {};
  var dontHandle = ['track','enableChannelsEvents','enableRootChannelsEvent','enableKeywordsEvents'];
  if(typeof options !== 'undefined'){
    for(var key in options){
      if(dontHandle.indexOf(key) === -1){
        result[key] = options[key];
      }
    }
  }
  result.track = this.trackedKeywords;
  return result;
}
```
- example usage
```shell
...
 */
var StreamChannels = function(apiClient, options) {
  helpers.checkStreamChannelsOptions(options, this);
  options.enableChannelsEvents = typeof options.enableChannelsEvents === 'undefined' ? true : options.enableChannelsEvents;
  options.enableRootChannelsEvent = typeof options.enableRootChannelsEvent === 'undefined' ? true : options.enableRootChannelsEvent
;
  options.enableKeywordsEvents = typeof options.enableKeywordsEvents === 'undefined' ? false : options.enableKeywordsEvents;
  helpers.preprocessKeywords(options, this);
  this.currentStream = apiClient.stream('statuses/filter',this._getOptionsToPassToApiClient(options));
  EventEmitter.call(this);
  addEvents(this.currentStream, this);
  this.options = options;
};

util.inherits(StreamChannels, EventEmitter);
...
```

#### <a name="apidoc.element.twitter-stream-channels.StreamChannels.prototype.getChannels"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>getChannels ()](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.getChannels)
- description and source-code
```javascript
getChannels = function () {
  return this.channels;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.twitter-stream-channels.StreamChannels.prototype.getChannelsKeywordsLowerCasedRegExp"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>getChannelsKeywordsLowerCasedRegExp ()](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.getChannelsKeywordsLowerCasedRegExp)
- description and source-code
```javascript
getChannelsKeywordsLowerCasedRegExp = function () {
  return this.channelsKeywordsLowerCasedRegExp;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.twitter-stream-channels.StreamChannels.prototype.getTrackedKeywords"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>getTrackedKeywords ()](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.getTrackedKeywords)
- description and source-code
```javascript
getTrackedKeywords = function () {
  return this.trackedKeywords;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.twitter-stream-channels.StreamChannels.prototype.start"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>start ()](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.start)
- description and source-code
```javascript
start = function () {
  this.currentStream.start();
  return this;
}
```
- example usage
```shell
...
  result.track = this.trackedKeywords;
  return result;
};

/**
 * Call this function to restart the stream after you called '.stop()' on it.
 *
 * Note: there is no need to call '.start()' to begin streaming. ' TwitterStreamChannels.streamChannels' calls .start() for you.
 * @method start
 * @returns {StreamChannels}
 */
StreamChannels.prototype.start = function() {
  this.currentStream.start();
  return this;
};
...
```

#### <a name="apidoc.element.twitter-stream-channels.StreamChannels.prototype.stop"></a>[function <span class="apidocSignatureSpan">twitter-stream-channels.StreamChannels.prototype.</span>stop (options)](#apidoc.element.twitter-stream-channels.StreamChannels.prototype.stop)
- description and source-code
```javascript
stop = function (options) {
  options = typeof options === 'undefined' ? {} : options;
  options.removeAllListeners = typeof options.removeAllListeners === 'undefined' ? false : options.removeAllListeners;
  this.currentStream.stop();
  removeEvents(this.currentStream, this, options);
  return this;
}
```
- example usage
```shell
...

//If you're really picky, you can listen to only some keywords
//stream.on('keywords/javascript',function(tweet){
//    console.log(tweet.text);//any tweet with the keyword "javascript"
//});

setTimeout(function(){
    stream.stop();//closes the stream connected to Twitter
	console.log('>stream closed after 100 seconds');
},100000);
'''

## API

You can find an API doc generated from the source code on [http://labs.topheman.com/twitter-stream-channels/](http://labs.topheman
.com/twitter-stream-channels/ "http://labs.topheman.com/twitter-stream-channels/").
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
