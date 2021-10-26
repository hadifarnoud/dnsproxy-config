# dnsproxy-config

[dnsproxy](https://github.com/AdguardTeam/dnsproxy) as a simple service

Example service using AdGuard Team's dnsproxy to provide encrypted transports to existing Pi-hole+Unbound deployments, can be easily modified to purpose.

## Usage
* Install dnsproxy binary

Note: The binaries I compile are for aarch64

If you are using another architecture, grab a binary from the [release page](github.com/AdguardTeam/dnsproxy/releases).
```
sudo wget https://github.com/saint-lascivious/dnsproxy-config/raw/master/usr/local/bin/dnsproxy -P /usr/local/bin/
```

* Create the service configuration directory

Create the /opt/dnsproxy directory
```
sudo mkdir /opt/dnsproxy
```

* Download the service configuration file
```
sudo wget https://raw.githubusercontent.com/saint-lascivious/dnsproxy-config/master/opt/dnsproxy/dnsproxy -P /opt/dnsproxy
```

* Install the dnsproxy service file
```
sudo wget https://raw.githubusercontent.com/saint-lascivious/dnsproxy-config/master/lib/systemd/system/dnsproxy.service -P /lib/systemd/system
```

* Create the dnsproxy configuration directory
```
sudo mkdir /etc/dnsproxy
```

* Download the dnsproxy configuration file
```
sudo wget https://raw.githubusercontent.com/saint-lascivious/dnsproxy-config/master/etc/dnsproxy/dnsproxy-config.yaml -P /etc/dnsproxy
```

* Change Pi-hole dnsmasq listening port

If listening for tcp/udp 53 you will need to ensure dnsmasq is not listening on the same port.
```
sudo wget https://raw.githubusercontent.com/saint-lascivious/dnsproxy-config/master/etc/dnsmasq.d/99-listening-port.conf -P /etc/dnsmasq.d
```

Restart Pi-hole
```
pihole restartdns
```

* Start the dnsproxy service

Enable the service
```
sudo systemctl enable dnsproxy
```

Start the service
```
sudo systemctl dnsproxy start
```

## Contact
* Discord
[SaintLascivious](https://discord.gg/NC7taVyn)

* Email
saint@sainternet.xyz

* IRC
[##saint-lascivious](https://webchat.freenode.net/##saint-lascivious)

* Reddit
[saint-lascivious](https://www.reddit.com/user/saint-lascivious)

![alt text][logo]

[logo]:https://vignette.wikia.nocookie.net/pokemon/images/7/76/265Wurmple.png "Using the spikes on its rear end, Wurmple peels the bark off trees and feeds on the sap that oozes out. This Pokémon's feet are tipped with suction pads that allow it to cling to glass without slipping."
