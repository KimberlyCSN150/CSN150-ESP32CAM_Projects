# Cybersecurity : CSN150
Project: ESP32 WiFi Scanner

## Purpose
Set up ESP32 and Arduino enviornment. Execute sketch " Wifiscanner". 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)

## Links to documentation and tools
https://lastminuteengineers.com/getting-started-with-esp32-cam/
https://lastminuteengineers.com/esp32-arduino-ide-tutorial/
##### Video 1: 

##### Other Links: 

##### AI GPTs used

## Steps I followed
Setting Up the Arduino IDE
Before you can program your ESP32-CAM, you need to prepare the Arduino IDE on your computer. This involves two main steps:

Installing the ESP32 Board
To work with the ESP32-CAM, or any ESP32-based board, in the Arduino IDE, you first need to install the ESP32 board package. This package adds all the necessary tools and libraries that let Arduino IDE understand how to program ESP32 devices.
Selecting the Board and Port
Now, connect your ESP32-CAM to your computer using either an FTDI adapter or the ESP32-CAM-MB board with a USB cable.
In the Arduino IDE, click the dropdown menu at the top and choose “Select Other Board and Port“. If you’re using an older version of the IDE, go to Tools > Board instead.
A list of boards will appear. From that list, select “AI-Thinker ESP32-CAM.”
Next, choose the correct COM port for your ESP32-CAM. If you’re not sure which one it is, here’s a quick trick: Unplug your ESP32-CAM and see which port disappears from the list. Then plug it back in and select that port.

ESP32-CAM Example 1 : Blink
Now that you’ve completed all the setup steps, you’re ready to run your first program on the ESP32-CAM!
Let’s start with the simplest program possible: the classic Blink sketch! This program makes the onboard Camera Flash LED blink on and off.
Once you’ve uploaded the sketch to the ESP32-CAM, the onboard Camera Flash LED should start blinking!
If you’re using an FTDI adapter, first disconnect it from the computer, then disconnect GPIO 0 from GND. After that, plug the adapter back into the computer.

Congratulations! Your ESP32-CAM is now running its first program.

ESP32-CAM Example 2 : Live Video Streaming Server
Now, let’s take things to the next level by turning your ESP32-CAM into a live video streaming server. It’s a fantastic demonstration of just how capable the ESP32-CAM really is!

You can find this example by navigating to File > Examples > ESP32 > Camera > CameraWebServer.
Before uploading, you’ll need to make a few small modifications to the code.

First, locate the section in the code where you must enter your Wi-Fi credentials. Replace the placeholders with your network’s SSID (name) and password. This information tells your ESP32 which network to connect to.
Next, you need to specify which camera model you’re using. Click on the “board_config.h” tab in the Arduino IDE. Since we’re working with the AI-THINKER model of the ESP32-CAM, you need to find the line that says “CAMERA_MODEL_AI_THINKER” and uncomment it. Make sure all the other camera model options remain commented out.

Once you’ve made these changes, go ahead and upload the sketch to your ESP32-CAM.

Accessing the Video Streaming Server
After uploading the sketch, open the Serial Monitor and make sure the baud rate is set to 115200. Then press the Reset button on your ESP32-CAM. If everything is working correctly, the ESP32 will connect to your Wi-Fi network and print out a message that says “Camera Ready!” along with the IP address that your router assigned to your ESP32-CAM

Now, open a web browser on your computer or phone and type in the IP address. Just make sure your device is connected to the same Wi-Fi network as the ESP32-CAM, or you won’t be able to reach it.
## Problems and Solutions
Note your problems or errors here.  Google any error you may come across, and not what you tried (even if it does not work), and what was the final answer. Document your errors and solutions that worked for you.  

You should see a web page hosted by the ESP32-CAM. To start watching the live video feed from your camera, simply click the “Start Stream” button.
On the left side of the web page, you’ll find various camera controls. You can adjust settings such as resolution, frame rate, brightness, contrast, and saturation to customize your video feed.
If you want to capture a single photo, just click the “Get Still” button. Keep in mind that when you do this, the image gets downloaded directly to your computer rather than being saved to the microSD card in the ESP32-CAM.

**Problem:** E (485) camera: Camera probe failed with error 0x105(ESP_ERR_NOT_FOUND)
Camera init failed with error 0x105
**Solution:**

### Example Problem
**Problem:** Arduino code will not load on ESP32 Cam.
**Solution:** Camera drivers were incorrect I needed to install the driver: [https://www.wch-ic.com/downloads/CH341SER_ZIP.html](https://github.com/martin-ger/esp32_nat_router).  I used file, "CH341SER.ZIP" and it worked.

## Final Report
