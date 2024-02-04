# A beginner’s guide to IoT with ESP32
<i>  The items linked are for Nepal but you can get the same in Amazon as well</i>

## Introduction to IoT

The Internet of Things (IoT) refers to a network of interrelated devices that connect and exchange data with other IoT devices and the cloud. It encompasses devices with sensors, processing ability, and software, all of which enable data exchange ([TechTarget](https://www.techtarget.com/iotagenda/definition/Internet-of-Things-IoT)).This network consists of physical devices, vehicles, appliances, and other objects embedded with sensors, enabling them to connect to the internet ([IBM](https://www.ibm.com/topics/internet-of-things)). IoT has become an integral part of modern technology, with billions of physical devices worldwide now connected to the internet ([ZDNet](https://www.zdnet.com/article/what-is-the-internet-of-things-everything-you-need-to-know-about-the-iot-right-now/)). This interconnected web of devices allows for smart and automated functionalities, impacting various aspects of our lives, from homes and industries to healthcare and transportation. For more, here is a video. 

## Introduction to ESP32

ESP32 is a microcontroller from Espressif Systems that combines the features of a microcontroller, Wi-Fi SoC, and Bluetooth SoC in a single chip. It has 2.4 GHz and 5 GHz Wi-Fi, Bluetooth 4.2, and can be programmed with Arduino, C++, or Micropython. It has a flash memory of 4MB and SRAM of 512KB, making it an excellent choice for IoT projects and prototyping.These features make the ESP32 an ideal choice for developing IoT projects, ranging from simple sensor applications to complex home automation systems.

---

### Prerequisites:

1. Install Arduino IDE : You can download and install Arduino IDE by clicking [here](https://www.arduino.cc/en/software).
    
    ![arduino ide.gif](A%20beginner%E2%80%99s%20guide%20to%20IoT%20with%20ESP32/arduino_ide.gif)
    

1. Installing ESP32 Add on in Arduino IDE
    1. In your Arduino IDE, go to Arduino IDE> Settings
    2. Enter the following into the “Additional Board Manager URLs” field: 
    
    ```basic
    https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
    ```
    
    ![setting up.gif](A%20beginner%E2%80%99s%20guide%20to%20IoT%20with%20ESP32/setting_up.gif)
    
    c. Then, click the “OK” button:
    
    d. Open the Boards Manager. 
        Go to **Tools** > **Board** > **Boards Manager…**
    
    e. Search for **ESP32** and press install button for the “**ESP32 by Espressif Systems**“:
    
    f. That’s it. It should be installed after a few seconds.
    
    ---
    

## **Materials Needed for Simple RC Car Project:**

1. <b> [ESP32 Development Board:](https://www.daraz.com.np/products/esp32-development-board-i113427460.html) </b> The brain of your project, the ESP32 microcontroller.
2. **Jumper Wires:** For connecting components on the breadboard. There are  say  three types of jumper wires:
    1. [Male-to-Male Jumper Wires:](https://www.daraz.com.np/products/40pcs-dupont-cable-jumper-wire-cable-male-to-male-1p-1p-254mm-20cm-i106172074.html) These wires have a pin (male) connector on both ends.
    2. [Male-to-Female Jumper Wires](https://www.daraz.com.np/products/male-to-female-connecting-wire-i127943733-s1034975424.html?spm=a2a0e.searchlist.sku.1.3aaa381dVJKTf3&search=1): One end has a pin (male) connector, and the other end has a socket (female) connector.
    3. [Female-to-Female Jumper Wires](https://www.daraz.com.np/products/female-to-female-dupont-jumper-wiresper-10-pcs-i122735612-s1033372100.html?spm=a2a0e.searchlist.sku.1.25e66d91t8i3h8&search=1): Both ends have socket (female) connectors.
3. <b> [Breadboard:](https://www.daraz.com.np/products/breadboard-small-400pts-i105462602-s1027189794.html?spm=a2a0e.searchlist.sku.5.171b162etyBUMx&search=1)</b> A platform for prototyping and connecting electronic components and to organize the circuits. 
4. **DC Motors:** Motors to drive the wheels of the car.
5. **Motor Driver:** To control the speed and direction of the motors.
6. **Wheels and Chassis:** Physical components for your car's structure.
7. **Battery Pack:** A power source for the motors, ensuring mobility.
8. **Remote Control (Optional):** If you want to control the car remotely, a simple RF or IR remote control module can be added.

PS: **Motor Smart Robot Car Chassis Set can be bought from [Supreme Light Technology](https://maps.app.goo.gl/aZk16LLR5g8wJSJt9)**

## **Optional [Materials Needed for Simple Bulb Project]**

1. <b> [ESP32 Development Board:](https://www.daraz.com.np/products/esp32-development-board-i113427460.html) </b> The brain of your project, the ESP32 microcontroller.
2. **Jumper Wires:** For connecting components on the breadboard. There are  say  three types of jumper wires:
    1. [Male-to-Male Jumper Wires:](https://www.daraz.com.np/products/40pcs-dupont-cable-jumper-wire-cable-male-to-male-1p-1p-254mm-20cm-i106172074.html) These wires have a pin (male) connector on both ends.
    2. [Male-to-Female Jumper Wires:](https://www.daraz.com.np/products/male-to-female-connecting-wire-i127943733-s1034975424.html?spm=a2a0e.searchlist.sku.1.3aaa381dVJKTf3&search=1) One end has a pin (male) connector, and the other end has a socket (female) connector.
    3. [Female-to-Female Jumper Wires:](https://www.daraz.com.np/products/female-to-female-dupont-jumper-wiresper-10-pcs-i122735612-s1033372100.html?spm=a2a0e.searchlist.sku.1.25e66d91t8i3h8&search=1): Both ends have socket (female) connectors.**
3. <b> [Breadboard:](https://www.daraz.com.np/products/breadboard-small-400pts-i105462602-s1027189794.html?spm=a2a0e.searchlist.sku.5.171b162etyBUMx&search=1) </b> A platform for prototyping and connecting electronic components.
4. <b> [LED Bulb:](https://www.daraz.com.np/products/led-5mm-mix-colors-pack-of-50-pcs-i104978871-s1026558433.html?&search=0?spm=a2a0e.pdp.recommend_2.5.3cf21cefsZn8xl&mp=1&scm=1007.38553.252219.0&clickTrackInfo=a79cdbed-2eb2-4c29-9c92-73fa6b6e95fe__104978871__10000489__cate__372903__0.12584627__0.12584627__0.0__0.0__0.0__0.0633163__4__null__null__null__null__null__null____130.0__0.03076923076923077__4.59375__64__126.0__273165,294830,323495,332334,338926,339834,390289,470812,515824,537206__null__null__null__3650.16544_955.3632_4559.21183__null__28556__null__0.0__0.0________null__null)</b> A light-emitting diode (LED) for the bulb simulation.
5. <b> [Resistor](https://www.daraz.com.np/products/ldr-sensor-3pcs-light-dependent-resistor-sensor-set-of-3-light-controlled-variable-resistor-photosensitive-sensor-3-pcs-i104074268-s1024874902.html?spm=a2a0e.searchlist.sku.2.19bb55b1f4rVCW&search=1):</b> To limit the current flowing through the LED.
6. <b> [Power Source:](https://www.daraz.com.np/products/metal-micro-usb-cable-i21133.html)</b> Depending on your ESP32 model, you may need a USB cable for power. But mostly it is micro usb. 

Resources: 

**[Getting Started with ESP32 Development Board.](https://www.youtube.com/watch?v=OXjNLBTY8So)**

**[Introduction to ESP32 Board - Getting Started ( Step by Step)](https://www.youtube.com/watch?v=aLEKiGNfHZw)**

**[How to Setup and Program ESP32 Microcontroller– Complete Guide](https://www.youtube.com/watch?v=AitCKcyjHuQ)**

**[How to use a BreadBoard - Electronics Basics 10](https://www.youtube.com/watch?v=fq6U5Y14oM4)**