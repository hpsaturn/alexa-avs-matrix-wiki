## Overview

If you want to try another provisioning method follow the instructions below.

## Instructions

1. Shut down the sample app by pressing **CTRL-C** while in the terminal window or command prompt where the sample app is running.
2. If you were using the Node.js server, shut it down by pressing **CTRL-C** in the terminal window or command prompt where the node server is running.
3. If you are running a wake word engine for the Raspberry Pi project, shut down the wake word engine by pressing **CTRL-C** in the terminal window or command prompt where the engine is running.  
4. In a text editor, open `{REFERENCE_IMPLEMENTATION}/samples/javaclient/config.json`
5. If your provisioning method was `companionApp`, in the `companionApp` object, delete the following key/value pairs:
   * `clientId`
   * `refreshToken`
6. If your provisioning method was `companionService`, in the `companionService` object, delete the following key/value pair:
   * `sessionId`
7. Change the `provisioningMethod` if you wish.
8. Save the `config.json`.
9. Follow instructions for building and running a companion service or companion app. Then relaunch the sample app.
   * [Build and Run Node.js Server]()
   * [Build and Run Android Companion App]()
   * [Build and Run iOS Companion App]()

## Resources

* [Alexa Voice Service](https://developer.amazon.com/public/solutions/alexa/alexa-voice-service)
* [API Documentation](https://developer.amazon.com/avs)  
* [Alexa Blog](https://developer.amazon.com/public/community/blog/tag/Alexa)
* [Terms and Agreements](https://developer.amazon.com/public/solutions/alexa/alexa-voice-service/support/terms-and-agreements)  
