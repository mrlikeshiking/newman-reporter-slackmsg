# newman-reporter-slackshooter

Custom [Newman](https://github.com/postmanlabs/newman) reporter to send message to [Slack](https://slack.com/)

<img src="https://github.com/jackcoded/newman-reporter-slackmsg/blob/master/testResults.png?raw=true" width="450"  height="550">

## Before you get started
- Install [Newman](https://github.com/postmanlabs/newman) ``` $ npm run i -g newman ```
- Create a [Slack incoming webhook url](https://api.slack.com/messaging/webhooks)
or
- Create a [Slack bot to send to channel or user dynamically](https://api.slack.com/messaging/sending)

## Installation
 ```CLI
 npm i -g newman-reporter-slackshooter
 ```

## Usage
```CLI
 newman run <collectionFile> -e <environmentFile> --suppress-exit-code -r slackshooter --reporter-slackshooter-webhookurl '<webhookurl>'
```

## Usage with channel override bot
```CLI
 newman run <collectionFile> -e <environmentFile> --suppress-exit-code -r slackshooter --reporter-slackshooter-webhookurl '<https://slack.com/api/chat.postMessage>' --reporter-slackshooter-token '<bearer token>' --reporter-slackshooter-channel '<channel or userid>'
```

## Reporter Options Optionals
```
 --reporter-slackshooter-messageSize '<messageSize>' e.g 150
 --reporter-slackshooter-token '<bearer token>' e.g xoxb-XXXXXXXXXXXX-TTTTTTTTTTTTTT
 --reporter-slackshooter-channel '<channel>' e.g #general
 --reporter-slackshooter-failuresChannel '<channel>' e.g. #alerts
 --reporter-slackshooter-collection '<collectionName> e.g test.json
 --reporter-slackshooter-environment '<environmentName> e.g env.json
 --reporter-slackshooter-reportingurl '<URL> e.g https://127.0.1/index.html

```


## Reporter Options
**webhookurl** 
Webhook URL to point to the slack api where results are published

**collection** 
Option to add the name of collection file onto the message

**environment**
Option to add the name of environment file onto the message

**messageSize**
Option to change the message size, defaulted to 100

**token**
Option to use bearer token for slack bots for channel override

**channel**
Option to select channel or user receive the result

**failuresChannel**
Option to select channel or user to receive failures
