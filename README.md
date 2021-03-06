# rpi-ttn-gateway
Raspberry PI TTN gateway image based on Hypriot.

## Hardware Preperation
* You need a Raspberry

## OS preparation
This image is made for and tested on a Raspberry Pi 3 together with a IMST-iC880 SPI LoRaWAN concentrator. Here are the steps to get the host environment ready for this image:
1. Download the latest HypriotOS from here: https://blog.hypriot.com/downloads/
2. Install it on a SD card. Etcher is a easy-to-use tool for this: https://etcher.io/
3. Put the SD card into your Raspberry Pi and power it up
4. Login with user pirate and password hypriot *Note*: default is a QWERTY keyboard. If you are using a QWERTZ keyboard make sure you use the correct 'y' in the password
5. Run `sudo apt-get update && sudo apt-get install raspi-config kbd`. During setup you can choose a different keyboard layout if you need
6. Run 
   ```bash
    docker run -it --privileged --net=host --restart=alway \
    -e GATEWAY_EUI=YOUR_MAC_ADDRESS \
    -e GATEWAY_LAT=YOUR_LATITUDE \
    -e GATEWAY_LON=YOUR_LONGITUDE \
    -e GATEWAY_ALT=YOUR_LATITUDE \
    -e GATEAY_EMAIL=YOUR_EMAIL \
    -e GATEWAY_NAME=YOUR_GATEWAY_NAME \
    ncagroup/rpi-ttn-gateway
    ```
    

## Running the container



## Optional: Building the image
To build the image run
```bash
docker build . 
