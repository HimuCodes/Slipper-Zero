# Slipper-Zero

This project introduces an universal tool for ESP32 platform for implementing various Wi-Fi attacks. It provides some common functionality that is commonly used in Wi-Fi attacks and makes implementing new attacks a bit simpler. It also includes Wi-Fi attacks itself like capturing PMKIDs from handshakes, or handshakes themselves by different methods like starting rogue duplicated AP or sending deauthentication frames directly, etc...

Obviously cracking is not part of this project, as ESP32 is not sufficient to crack hashes in effective way. The rest can be done on this small, cheap, low-power SoC.

I made this project for my value addition program inspired by Flipper zero and Marauder by JustCallMeKoko and Risinek's ESP32 Penetration Tool.
This project also leverages these functionalities by using a mobile phone signal detector and packet monitor ona TFT ST7735 Display. This project uses ESPIDF tool to flash the custom firmware based for this project.

This is just a prototype which may conatin bugs.

![WhatsApp Image 2024-04-17 at 12 35 12 PM](https://github.com/HimuCodes/Slipper-Zero/assets/110077858/4c34487a-a80b-440a-98ef-4684af31dbd5)
The above image is just a joke.
## Features
- **PMKID capture**
- **WPA/WPA2 handshake capture** and parsing
- **Deauthentication attacks** using various methods
- **Denial of Service attacks**
- Formatting captured traffic into **PCAP format**
- Parsing captured handshakes into **HCCAPX file** ready to be cracked by Hashcat
- Passive handshake sniffing
- Easily extensible framework for new attacks implementations
- Management AP for easy configuration on the go using smartphone for example
- And more...

## Usage
1. Power ESP32
2. Management AP is started automatically after boot
3. Connect to this AP\
By default: 
*SSID:* `ManagementAP` and *password:* `mgmtadmin`
4. In browser open `192.168.4.1` and you should see a web client to configure and control tool like this:
   The Web Ui for the project was taken from Wifimanager.h and risinek's webui for his own tool.
   We used this because our display was not working properly.
   ![ui-config](https://github.com/HimuCodes/Slipper-Zero/assets/110077858/dd2774c0-cb54-472e-a946-e1901a7b40a9)
