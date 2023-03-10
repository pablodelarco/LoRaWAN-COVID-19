# LoRaWAN-COVID-19
 IoT CO2 measurement system for COVID-19 prevention based on LoRaWAN

<h2>Introduction</h2>
This is an IoT project based on ESP32 devices that measure CO2 levels, temperature and humidity. This data is sent to a gateway via LoRaWAN communication, where it can be visualised with an IoT dashboard.


<h2>Device Setup</h2>
The final node or device chosen for this project is the Heltec Wi-Fi LoRa 32 V2.1, the CO2 sensor MH-Z19B and the humidity temperature sensor DHT22. In addition, the MCU has an 868 MHz antenna to transmit the information to the gateway. To protect all the components, it is proposed to build a housing using 3D printing, as this allows customised parts to be designed.



![image](https://user-images.githubusercontent.com/63775967/208689677-cccc398a-689d-4d11-8181-ca14238ee3c0.png)

![image](https://user-images.githubusercontent.com/63775967/208689914-beb74227-a8fd-457c-8648-2a8fe3cd0048.png)

![image](https://user-images.githubusercontent.com/63775967/208690064-ba55984e-7e92-4535-97ca-7bf03a02c3e4.png)


<h2>Gateway setup</h2>

![image](https://user-images.githubusercontent.com/63775967/208690221-10f963db-c654-4221-885f-a5a660df504a.png)

The operating system chosen for the Raspberry Pi is Balena OS, which offers the following interface for managing the most important parameters:

![image](https://user-images.githubusercontent.com/63775967/208690498-38c624bf-be60-4fd5-ac5d-3d720eb7fd48.png)

A 3D printed enclosure has also been produced to protect the gateway:

![image](https://user-images.githubusercontent.com/63775967/208690833-9e37cf0a-6f16-41ea-96f6-f37910d6d4e4.png)

![image](https://user-images.githubusercontent.com/63775967/208691574-85450093-3431-47a1-b773-7f787e4fa46c.png)


<h2>TTN Server configuration</h2>

The developers of The Things Network have created a server capable of managing the data transmitted between nodes and gateways, as well as being able to register these devices free of charge. In this section, we will explain step by step how to register both a gateway and a node in the TTN network.

The first thing to do is to access this link https://account.thethingsnetwork.org/register to create an account on the TTN website. Once we have logged in, we must enter our name, email and password. Once we have done so, we go to our avatar and select the "Console" option, as shown in the following figure:

![image](https://user-images.githubusercontent.com/63775967/208692032-88e594d9-1ad0-49d5-8b17-d47b6f83dfb7.png)

Next, it will be shown 2 options, "Applications" and "Gateways". This time we will start by configuring the end device, so we select "Applications".

![image](https://user-images.githubusercontent.com/63775967/208692256-29b96ee9-bb58-4814-b1e5-57784ca61c33.png)

Before registering a node in TTN, we need to create an application. These allow you to manage different devices and facilitate device management. To create one, we must enter a name, a description (optional) and the App EUI, although the latter is generated automatically. When we have completed the data, we click on "Add application".

![image](https://user-images.githubusercontent.com/63775967/208692895-984378a1-85e7-4ced-bcfa-984cc02d9c22.png)

Next, a menu will appear where we will be able to manage the different parameters of our application. In order to register a node, we must click on the upper tab called "Devices".

![image](https://user-images.githubusercontent.com/63775967/208693078-f7b5b10a-172b-461e-81d7-15df91ee9211.png)

Once we have accessed the "Devices" option, we select the "register device" option and the following menu will appear device" and the following menu will appear:

![image](https://user-images.githubusercontent.com/63775967/208693217-9537b19e-c7cd-4ffb-b38d-771a91946bd8.png)

The parameters that must be entered are:
- Device ID: This is the name by which we are going to identify our node within the application. the application.
Device EUI: Unique identifier for each device within the TTN network. We can write it We can write it ourselves or we can generate it randomly. It is made up of 8 bytes.
- App Key: Made up of 16 bytes, this is a code that ensures communication between the node and the network. communication between the node and the TTN network. Like the Device EUI, it can be written by us or randomly created by us. or we can create one at random.

When we have completed all the fields, click on the "Register" button and we will have registered our node in TTN. The figure shows the menu where we can manage the different parameters of our node, such as the name we have assigned it, the activation method (OTAA in this case), or the necessary keys to connect it to the TTN network.

![image](https://user-images.githubusercontent.com/63775967/208693649-ea6b96bc-d1ab-4234-8122-2e938f27851a.png)



