# LeLamp-Extend-Board

Extend board for project [LeLamp](https://github.com/humancomputerlab/LeLamp/tree/master), Easy and quick assembly


![](./assets/LeLamp-V1.0.png)

## Overview

LeLamp Extend board consists of five main interface: the **5V Power Input**, the **LED Matrix**, the **GPIO13** and the **I2C**, See the figure below.

![](./assets/LeLamp_tag.png)

## How to get it
- ### Proofing using the provided source files
- ### [PCBWay](https://www.pcbway.com/project/shareproject/LeLamp_Expansion_Board_38a28335.html)
- ### Buy on [Aliexpress bewait ]() or [淘宝](https://e.tb.cn/h.SQTekpxcpq8GLRg?tk=7IRnf2EZkhV)


## Installation Steps

### 1. Setup

```bash
    git clone -b v6.12 https://github.com/HinTak/seeed-voicecard
    sudo ./install.sh
    sudo reboot
```

Test the microphone setup:

```bash
    # Record test
    arecord -D plughw:CARD=seeed2micvoicec,DEV=0 -r 16000 -c 1 -f S16_LE -t wav -d 5 test.wav
    
    # Playback test
    aplay -D plughw:CARD=seeed2micvoicec,DEV=0 test.wav
    
    # Access mixer settings
    alsamixer -c seeed2micvoicec
```



### 2. Install Required Packages

```bash
    sudo apt-get update
    sudo apt-get install --no-install-recommends git python3-venv libopenblas-dev
```

### 3. Check if your device is enabled

```bash
   aplay -l
```

The expected output should be like this:

```bash
   card 2: seeed2micvoicec [seeed2micvoicec], device 0: 1f000a4000.i2s-tlv320aic3x-hifi tlv320aic3x-hifi-0 [1f000a4000.i2s-tlv320aic3x-hifi tlv320aic3x-hifi-0]
   Subdevices: 1/1
   Subdevice #0: subdevice #0
```

Afterwards, you can set up the sound level with the following command:

```bash
   alsamixer
```

Inside alsamixer, you can F6 to select device `seeed2micvoicec`. The audio setting to be edited is `Speaker`, `PCM Play`, `Mono Out`. This audio setting muted by default, which you can unmute by typing `M`.

![img.png](assets/alsamixer_orin.png)

![img.png](assets/alsamixer_change.png)