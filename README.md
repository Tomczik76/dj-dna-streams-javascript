# dj-dna-streaming-javascript
DNA Streaming Client - written in Javascript.

## How To Use

#### Installing

Install this at your project root by invoking the following command line:

~~~~
npm install git+https://git@github.dowjones.net/syndicationhub/dj-dna-streaming-javascript.git --save
~~~~
 
 or 

~~~~
npm install --save dj-dna-streaming-javascript --registry http://registry.npm.wsjfdev.dowjones.net/
~~~~

#### Add Code to Subscribe to a DNA Topic or Two:

> const djDnaStreaming = require('dj-dna-streaming');
>
> const onMessageCallback = function(msg, topic) {
>    console.log('One incoming message:' + JSON.stringify(msg.data));
>    console.log('Incoming message\'s topic: ' + topic);  
> };
>
> djDnaStreaming.subscribe(['topic-1', 'topic-2'], onMessageCallback);


#### Execute with Environment Variables

When executing code that invokes this module ensure you have set the following environment variables -- GOOGLE_CLOUD_AUTHENTICATION, GCLOUD_PROJECT and SUBSCRIBER_NAME.

###### GOOGLE_CLOUD_AUTHENTICATION

This environment variable should hold the file path of your Dow Jones provided security json file (googleApplicationCredentials.json).

###### SUBSCRIBER_NAME

Set this environment variable to your Dow Jones provided subscriber name.

###### GCLOUD_PROJECT (optional)

Most users will not need to use this variable. If you do not set this environment variable the code will use the default Dow Jones DNA Google Cloud production project name.

###### Example Execution Command (MacOS)

````
export GOOGLE_APPLICATION_CREDENTIALS=./googleApplicationCredentials.json && export GCLOUD_PROJECT=djsyndicationhub && export SUBSCRIBER_NAME=your-company-name-here && node index.js
````
