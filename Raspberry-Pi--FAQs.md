### I got the Raspberry Pi working with AVS, but I can’t hear the audio response from Alexa

Check to see if you are seeing the response coming through on the Terminal and if you see the response cards on your Alexa app. If yes, you probably need to force audio through local 3.5mm jack, instead of the HDMI output (this can happen even if you don’t have an HDMI monitor plugged in).

To force audio through local 3.5 mm jack, open Terminal, and type

	sudo raspi-config

See [Raspberry Pi Audio Configuration](https://www.raspberrypi.org/documentation/configuration/audio-config.md)

---

### How do I find the IP address of my Raspberry Pi?

	hostname -I

---

### Unable to fetch errors -
If you run into some "Unable to fetch" errors while trying to install VLC, try the following -

	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get install vlc-nox vlc-data

---

### Having issues with npm
If you run into some "npm not found" errors after installing node (older versions of Raspbian's node), try the following -

	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get install npm

---

### What if I cannot find an ethernet port for the pi?

Check out this url on how to bridge the connection between a laptop's wifi connection and the ethernet port on your pi.
https://www.hackster.io/Anwaarullah/sharing-wifi-with-raspberry-pi-using-a-lan-cable-ae1f44

---

### What does the ssl.cnf file look like?
[Here's](https://gist.github.com/ajotwani/a0d54110a968c984fd0b) what the ssl.cnf file would look like, replacing country, state, locality with your respective info.

###  “Cannot connect to the Companion Service” errors
This could be because of one of 3 things -


1. **Bad certificate** - which could be a result of -
	- Bad ssl.cnf file (See FAQ above for what it should look like),
	- incorrect java version,
	- possibly wrong passphrase in the config.json file,


2. **Incorrect Product id** - Make sure that these values are the same -
	- Device Type Info -> [Device Type ID](https://github.com/amzn/alexa-avs-raspberry-pi#34-register-your-product-and-create-a-security-profile) on the Amazon Developer Portal, and
	- Product ID in SSL cert generation (when prompted by [generate.sh](https://github.com/amzn/alexa-avs-raspberry-pi#4---generate-self-signed-certificates)), and
	- Product ID in [config.json](https://github.com/amzn/alexa-avs-raspberry-pi/blob/master/samples/javaclient/config.json)
	- the "key" in the products "key":["value"] pair in [config.js](https://github.com/amzn/alexa-avs-raspberry-pi/blob/master/samples/companionService/config.js), and

3. **Incorrect DSN** - Make sure that these values are the same -
	- dsn in [config.json](https://github.com/amzn/alexa-avs-raspberry-pi/blob/master/samples/javaclient/config.json), and
	- the "value" in the products "key":["value"] pair in [config.js](https://github.com/amzn/alexa-avs-raspberry-pi/blob/master/samples/companionService/config.js)

4. The Companion Service isn’t actually [running](https://github.com/amzn/alexa-avs-raspberry-pi#8---run-the-server).

___
