
# pokerwars.io-starterbot-python
This is a simple example of how you could implement a pokerwars.io bot with Python and [Bottle](https://bottlepy.org/docs/dev/). This bot will fold every hand, you should change this and try to implement your own strategy!

## Quick start
A few requirements to play:
- have [python](https://www.python.org/) installed
- make sure that the computer where your bot runs is visible from the internet, so we can communicate with them. [This is a useful service](http://canyouseeme.org/) to double check this. Bot default port is `3000`, but you can change this on the `server.js` file. If you need help to open a port on your router [check this guide](https://www.noip.com/support/knowledgebase/general-port-forwarding-guide/) or [contact us](mailto:contact@pokerwars.io). We are always willing to help you.
- [Register with us](https://www.pokerwars.io/) and retrieve your [API token](https://www.pokerwars.io/token) and [username](https://www.pokerwars.io/profile).
- check out this repo with git or download it from [this link](https://github.com/pokerwars/pokerwars.io-starterbot-python/archive/master.zip).
- in the code you just downloaded, rename `.env_example` as `.env` and update with your username, API token and bot ip address:
```
USERNAME=insert here your bot username, find it at https://www.pokerwars.io/profile
API_TOKEN=insert here your api token, find it at https://www.pokerwars.io/token
BOT_ENDPOINT=insert here your bot ip address. i.e.: http://1.2.3.4:3000
```

Now you can implement your own poker strategy and play!

## Play!
Now you are ready to run the bot!

Install dependencies:
```
$ pip install -r requirements.txt
```

Run the bot:
```
$ python starterbot.py
```

The bot will try to subscribe to pokerwars.io when it starts up. If no errors happens, it will start playing straightaway, otherwise you should see an error. The most common is that we cannot see your bot, please double check [your bot is visible from the internet](http://canyouseeme.org/) and [you have configured your router correctly](https://www.noip.com/support/knowledgebase/general-port-forwarding-guide/). If you do not have access to your router or your bot is behind a firewall, try [ngrok](https://ngrok.com/).

### Playing on Glitch.com?
It's easy:

- Import this repo into a new Glitch project
- Check the Live App URL for your project under `Share` (it will look like https://<MY_POKERWARS_BOT>.glitch.me), you will use it as your BOT_ENDPOINT
- Update your `.env` file as described above
- Start remixing!

Have fun!

## Bot subscription to pokerwars
When the bot starts up, the ```subscribe()``` method waits for its ```/pokerwars.io/ping``` endpoint to become available before subscribing the bot with pokerwars.io. This lets us know that your bot is ready to play and if we can ping your bot then it will be added to the next available tournament.

If the subscription request is not accepted or fails, for whatever reason, the bot will exit.

## Extending this bot
If something is not clear in this code, refer to also to [our documentation](https://www.pokerwars.io/docs) for the structure and content of the data we send to your bot. How you choose to manipulate that information to inform your bot's strategy is up to you!
