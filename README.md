# polybar-crypto
A *polybar script* that displays the price of various **crypto-currencies**.

A fork from willHol/polybar-crypto with the following changes:

- Returns an empty string if API request fails, removing output if no internet connection is available.
- Remove **cryptocoins** icon font and uses the coin ticker label instead.
- Add an additional mode which only queries a single coin. Each time the program is run a new coin from the list is chosen.

![screen](https://user-images.githubusercontent.com/24377188/31326832-34dd06de-ad27-11e7-908f-9e7d72398eb7.jpg)


# Setup
```
git clone https://github.com/stuianna/polybar-crypto.git &&
    cd polybar-crypto &&
    cp ./{crypto-config,crypto.py} ~/.config/polybar
```

Then in `~/.config/polybar/config`:

```
[bar/top]

...

modules-right = crypto

...

[module/crypto]
type = custom/script
interval = 300
exec = /home/<user>/.config/polybar/crypto.py

```
Additionally, you may need to change this line in `crypto.py` to match the correct location.

```
#Change this to the full path of your crypto-config file if necessary
configFile = '/home/<user>/.config/polybar/crypto-config'
```


# Example Configuration

`~/.config/polybar/crypto-config`
```
[general]
base_currency = AUD
display = percentage
mode = cyclic
ticker = bitcoin

[bitcoin]
icon = BTC

[ethereum]
icon = ETH

```

## Display Modes

`display = price`

![screen](https://user-images.githubusercontent.com/24377188/31331319-4ef14406-ad3e-11e7-9242-12440ef96774.jpg)

`display = percentage`

![screen](https://user-images.githubusercontent.com/24377188/31331342-65e40428-ad3e-11e7-88e0-3b87921805c7.jpg)

`display = both`

![screen](https://user-images.githubusercontent.com/24377188/31331368-80faac76-ad3e-11e7-9977-e86b1eebe401.jpg)
