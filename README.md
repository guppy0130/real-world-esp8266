# Real World ESP8266

## A collection of ESP8266-powered real-world applications

### Usage

```bash
git clone # clone the repo
git submodule init # initialize submodules
git submodule update # fetch submodules
```

You can also choose to obtain individual modules from [Gitlab](https://gitlab.com/real-world-esp8266).

### Hub setup

This is optional, but recommended if you have a limit to the number of devices you can add to the network, or if you want to centralize the ESPs under one network. Each Hub can take up to 8 devices according to the [spec](https://bbs.espressif.com/viewtopic.php?f=46&t=481&p=1832&hilit=max_connection#p1832), but Hubs may be nested (theoretically, untested) at a performance/latency cost (probably minimal, but again, untested).

1. Designate one ESP8266 to be the Hub
2. Upload the Hub specific code, replacing variable values as fit
3. Attach other ESP8266s and test.

Be wary of memory issues! I found that if the DELAY variable is set too high (more than 250), the Hub runs out of free space and crashes.

### Statsd setup

If you choose to not send metrics to the Hub for relay, you can send them to your statsd servers instead. However, should your statsd server change IP addresses, you will need to update all devices accordingly (whereas if there was a single Hub interfacing with the server, only one device would need to be updated).
