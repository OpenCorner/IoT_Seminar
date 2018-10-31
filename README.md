# GoogleAssistance_demo
You might have used google assistants app to play music, to get some information and for other stuff. But your google assistant can do more, than these. Now you can use your google assistant to control your home appliances (here we have LED in place of home appliance) by just saying:   "OK Google, Lights ON"  That's it.

**REQUIREMENT :**

**HARDWARE:** 
Bread Board Wemos D1 Mini Board, Led, Resistors, Relay Module (Need to Buy If We Are Connecting Home Appliance), USB Cable

**SOFTWARE:**
Arduino Ide, Google Assistant and IFTTT App in Your Smart Phone, an Active Account on Adafruit.io Mqtt Broker
LIBRARY:ADAFRUITIO_MQTT_LIBRARY YOU CAN DOWNLOAD IT FROM HERE :https://github.com/adafruit/Adafruit_MQTT_Library

**Control your home appliances from anywhere with your Google asssistant!!!**

Let's start your journey with our OPENCORNER’s hardware kit!!
Open that Kit box.
What do you have??
As you can see in that box there is one blue colour Board along with 2 LEDs, few resistors and jumper wires as shown below:
![image](https://user-images.githubusercontent.com/44518572/47646163-1266b400-db99-11e8-943d-aa068b7e6044.png) 
![image](https://user-images.githubusercontent.com/44518572/47646187-227e9380-db99-11e8-847c-cb022c65305e.png) 
![image](https://user-images.githubusercontent.com/44518572/47646240-4b9f2400-db99-11e8-9f20-db82629f11d4.png) 


**Introduction:**

You might have used google assistants app to play music, to get some information and for other stuff. But your google assistant can do more, than these. Now you can use your google assistant to control your home appliances (here we have LED in place of home appliance) by just saying: 

"OK Google, Lights ON"

That's it.
 
**Let’s see how to make this possible,**

**REQUIREMENT:**

**HARDWARE:**
 Bread Board Wemos D1 Mini Board, Led, Resistors, Relay Module (Need to Buy If We Are Connecting Home Appliance), USB Cable
 
**SOFTWARE:**
 Arduino Ide, Google Assistant and IFTTT App in Your Smart Phone, an Active Account on Adafruit.io Mqtt Broker
PROCESS:
Hardware Connection
Getting Arduino IDE ready for programming
Configuring Adafruit.io
Coding
IFTTT (connecting google assistant with Adafruit.io MQTT broker)

**Hardware Connection:**

•	As you can see on the board there is lots of pin available (i.e. analog pins, digital pins, TX, RX, 5V, 3.3 and ground pins)

•	Here we are going to use digital pins D1 and D2.

•	Let’s connect components as shown in below figure:


![4 in hardware connection 1](https://user-images.githubusercontent.com/44518572/47649267-ba34af80-dba2-11e8-9137-e43e0938e096.png)

![5 in hardware connection 2](https://user-images.githubusercontent.com/44518572/47649272-bef96380-dba2-11e8-8631-1f337716b1b6.png)

  If you have relay module than make connection as shown in figure with your home appliance. (here we are using bulb)
  

    WEMOS D1 mini                  Relay Board
    
    
       5V                 -----       VCC
       
       
      GND                 -----       GND
      
      
     IN (signal pin)    -----    D1 or *any digital pin
(Note: If you are using any other pin you have to change that pin configuration in given code.)

**Getting Arduino IDE ready for programming:**

![6 getting arduino ide ready for programmuing](https://user-images.githubusercontent.com/44518572/47649730-28c63d00-dba4-11e8-8fba-3d70d82461d7.png)
 
Download ARDUINO IDE from here  (according to your system) if you have windows system then just click here
Install ARDUINO IDE to your system.

Once setup is done we need to configure ESP8266 to use it with Arduino IDE

Now Open ARDUINO IDE.

**Step 1:** 
Copy this link http://arduino.esp8266.com/stable/package_esp8266com_index.json
Now go to file->preferences->Additional Boards Manager URLs
![7 preferences and additional board manager](https://user-images.githubusercontent.com/44518572/47649734-2cf25a80-dba4-11e8-8dbe-5ef7e40fe2e1.png)
 
 
**Step 2:**
Go to Tools->boards->boards manager, search ESP8266 and install esp8266 board.

![8 installing esp8266 in board manager](https://user-images.githubusercontent.com/44518572/47649750-37145900-dba4-11e8-9bac-0d9fb4a7bcbf.png)
 
Once installation is done you should be able to see ESP8266 Modules in Toolsboards.
 If "Yes" then Congratulations, you are ready to code!!

Let’s Start Coding......

**Step 3:**
Connect Wemos D1 mini to your computer via USB cable


**Step 4:** Download this code and open with Arduino IDE


**Step 5:** Go to Tools->boards->ESP8266 and Select Wemos D1 mini


**Step 6:** Select port COMX of your board
To check Port Go to device manager, you should be able to see your device under ports along with port number 
 
 ![9 device manager port](https://user-images.githubusercontent.com/44518572/47649753-3aa7e000-dba4-11e8-8a16-37f9e22606e2.png)

Here wemos d1 mini is connected on COM6 
Now select COM port on Arduino ide like this:

![10 port selecting in arduino](https://user-images.githubusercontent.com/44518572/47649756-3d0a3a00-dba4-11e8-8f01-6adff0341953.png)  
 

**Configure Adafruit.io**

**Step 8:**
Now we need a MQTT broker. There are many broker for MQTT but we have used Adafruit MQTT broker. It’s quite simple and its UI is also great. To use Adafruit MQTT broker, first of all you need to make an account on Adafruit.io.
 1. First sign up for ACCOUNT 
![11 configuring adafruit io 1](https://user-images.githubusercontent.com/44518572/47649759-3f6c9400-dba4-11e8-9b5a-ab9b2e67116a.png) 

2. Then LOGIN on Adafruit.io.
You can see something like this after login.

 
![12 configuring adafruit io 2](https://user-images.githubusercontent.com/44518572/47649769-45627500-dba4-11e8-865f-db936a727d62.png)
 
3.  Click on Action and Create new Dashboard as shown here
![13 configuring adafruit io 3](https://user-images.githubusercontent.com/44518572/47649777-4a272900-dba4-11e8-91d6-6b50432c09b0.png) 

Here we are creating dashboard name testing.

![14 configuring adafruit io 4](https://user-images.githubusercontent.com/44518572/47649781-4d221980-dba4-11e8-9a76-8a334aa69a2d.png) 
 
4. Now you can see "testing “dashboard that we have created:
 
![15 configuring adafruit io 5](https://user-images.githubusercontent.com/44518572/47649787-501d0a00-dba4-11e8-94de-00e61486e477.png)

As you can see there are many options available on the right corner of the page to edit the blocks, add new blocks, get the key, etc.

5. Now we will start with making a new button on the dashboard. For that click on the second button i.e. create a new block. It will show this window.
There are number of blocks to be added in this window like toggle button, push button, slider etc. In our project we will be using the first block i.e. toggle button. Click on create button and you will get following options.
 
![16 configuring adafruit io 6](https://user-images.githubusercontent.com/44518572/47649789-527f6400-dba4-11e8-9874-8873519fb796.png)

 
6. Than you have to provide feed name which should be unique because this feed name is nothing but the topic which clients will be subscribing.
![17 configuring adafruit io 7](https://user-images.githubusercontent.com/44518572/47650039-0aad0c80-dba5-11e8-8afd-55a2332b60a6.png)
 
I have given name of the feed as light. Then click the create button. Created feed name will be added, then select that feed name. Then click on next step. You will see something like this.

7. Fill the details as given in following image
 
![18 configuring adafruit io 8](https://user-images.githubusercontent.com/44518572/47650046-113b8400-dba5-11e8-9e88-6facfac2e08c.png)
 
 
8. You can see toggle button with "LIGHT" as a topic and "1" and "0" as the values.
![19 configuring adafruit io 9](https://user-images.githubusercontent.com/44518572/47650054-14367480-dba5-11e8-88c4-e4f2763c12f6.png)
 
9.Follow this same procedure to create topic "light1" then you will see two toggle buttons on dashboard as follow.
![20 configuring adafruit io 10](https://user-images.githubusercontent.com/44518572/47650129-4b0c8a80-dba5-11e8-9ec8-2564f07dd418.png)  


10. Now click on KEY icon on right corner of the dashboard. You will see prompted window showing USERNSME and KEY. 
Note: Copy and paste these details somewhere because we are going to use these detail in code for connection purpose.
![21 configuring adafruit io 11](https://user-images.githubusercontent.com/44518572/47650139-4fd13e80-dba5-11e8-9c9a-166ca99beb31.png)
  
That’s it. You are done with the broker side. No complexity, nothing. Only simple and great UI and that’s why we like adafruit broker. You can even drag and resize the block according to your need.
 
Coming back to Arduino
Step9: Download “GoogleAssistance_demo” code from here by clicking on “Clone or download” (download zip). Unzip this folder and open that code in Arduino IDE.
Now download “Adafruit_MQTT_Library” from here. Click on “Clone or download.”

![22 coming back to arduino downloading adafruit library 12](https://user-images.githubusercontent.com/44518572/47650143-52cc2f00-dba5-11e8-94ca-9bf65c7c824c.png)
 
Now follow this step to add this library into our ARDUINO IDE.
Go to Sketchinclude libraryadd zip library than navigate to that library then open. 
You get message if library is successfully added to Arduino. 

Now, Make following changes, write down you router SSID AND PASSWORD at

 #define WLAN_SSID   “YOUR ROUTER SSID"
#define WLAN_PASS   "YOUR ROUTER PASSWORD"
![23 changes in arduino code 13](https://user-images.githubusercontent.com/44518572/47650146-552e8900-dba5-11e8-98ec-89797f5c6eb3.png)

Copy and place your adafruit’s USERNAME and KEY at this location in code.

#define AIO_USERNAME   "YOUR USERNAME"                // WRITE YOUR ACCOUNT USERNAME HERE
#define AIO_KEY                 "YOUR PASSWORD"                // WRITE AUTOGENERATED KEY HERE

Step10: Click COMPILE button
If you don’t get any error code can now be uploaded

Step11: Click UPLOAD button
Step12: Open Serial Monitor by clicking on search type icon as you can see in right corner. A small window is prompted as shown below. Make configuration as highlighted in figure. As you can see wifi and mqtt both are connected.

![24 serial monitor 14](https://user-images.githubusercontent.com/44518572/47650150-5790e300-dba5-11e8-9f09-1e20e07b7015.png)
         
IFTTT APP

Now install IFTTT app in your smart phone.
Make an account on IFTTT applet service.

IFTTT stands for “IF THIS THAN THAT” 
If we relate this to our example if this thing is happening than do this thing.
In this process we going to merge our “google assistant” to our “Adafruit mqtt broker”
Using IFTTT applet service.
So when we say “ok google lights on” this phrase send (publish) data to mqtt broker feed 
And our device which is already subscribed to this feed or topic will receive this data and lights becomes OFF.

Let’s see how to merge both this services.

Step 1: First open IFTTT application that you have already installed.
Step 2: Now Go to “My Applets”.
Step 3: On “My Applets”, in the right corner there is a “+” sign, click on that to create your own Applet.

![25 iftt myapplet 1](https://user-images.githubusercontent.com/44518572/47650152-59f33d00-dba5-11e8-9509-6977aad212a2.png)
                                       
Step 4: Now click on +this and search for GOOGLE assistant service and click on google assistant service to add as our input.Now click on say a simple phrase.
 
![26 iftt myapplet2](https://user-images.githubusercontent.com/44518572/47650157-5bbd0080-dba5-11e8-8dfb-a6699cd9b460.png)
![27 iftt myapplet 3](https://user-images.githubusercontent.com/44518572/47650160-5e1f5a80-dba5-11e8-962e-5bd18be2491a.png)  
![28 iftt myapplet 4](https://user-images.githubusercontent.com/44518572/47650161-5fe91e00-dba5-11e8-9524-5eeae2841584.png) 
![29 ifttt myapplet5](https://user-images.githubusercontent.com/44518572/47650164-62e40e80-dba5-11e8-833e-309a4437ae30.png)  

Now you have got one screen with some question.
1st Question: 
What do you want to say?
        Just write which command you want to give to turn ON the light.
        Write “lights ON” or”turn on the light google”
2nd Question:
 What do you want the assistant to say in response?
     You can write any phrase here like “Ok done lights are on” or “JO HUKUM                    
     MERE AAKA”
    Then click on create trigger.
Now you can see google assistant is added in place of +this.
![30 ifttt myapplet6](https://user-images.githubusercontent.com/44518572/47650167-65466880-dba5-11e8-9ac7-2370505231d0.png)

![31 ifttt myapplet 7](https://user-images.githubusercontent.com/44518572/47650172-68d9ef80-dba5-11e8-8c32-5b82073bd00d.png)  
Step 5: Now click on +that and search for adafruit and click on ADAFRUIT service.
Then click on send data to adafruit IO button
Now you will see something like this:
Here, we have to provide feed name that we have already created on ADAFRUIT.
Just click on below feed name you will see light and light1 feed that we have created
Select light feed.
Now type “1” in data to save field to turn on the light. (If you remember we have given 1 at button on text at toggle button configuration on adafruit.io) 
Now click on create action.
Now click on finish.
![32 iftt myapplet 8](https://user-images.githubusercontent.com/44518572/47650177-6aa3b300-dba5-11e8-9735-d7e63785b45c.png)
![33 ifttt myapplet 9](https://user-images.githubusercontent.com/44518572/47650181-6d060d00-dba5-11e8-95ab-e7a05e9eb31b.png)

Step 6: After that you will be prompted to adafruit site now click on authorize to give access.  

![34 ifttt myapplet 10](https://user-images.githubusercontent.com/44518572/47650182-6ecfd080-dba5-11e8-9c8d-9a0cc2f75dc4.png)

Now go to the dashboard and click on “services”.
![35 ifttt myapplet 11](https://user-images.githubusercontent.com/44518572/47650184-70999400-dba5-11e8-9904-e667edddc00f.png)
 
You will see lots of services, now click on get started button given below IFTTT service.

![36 ifttt myapplet 12](https://user-images.githubusercontent.com/44518572/47650185-72635780-dba5-11e8-8108-6a9909bba74f.png)
 
You can see IFTTT is connected with your adafruit account. 
![37 ifttt myapplet 13](https://user-images.githubusercontent.com/44518572/47650187-742d1b00-dba5-11e8-88da-eac73600f110.png)
 
Follow this whole procedure again from Step2 to Step5 to create another applet for turning off the light.
You just have to change 2-3 things.
Give input command “lights off” at google assistant setting as discussed above for “lights on” and write “0” at data to save field this time at send data to adafruit page in IFTTT app
 
Everything is done.now, just say “ok google” then you will see something as shown below on your mobile screen

![38 google assistant last image](https://user-images.githubusercontent.com/44518572/47650190-768f7500-dba5-11e8-88d6-217d280e7bbc.png)
 
Now just say “lights on” (say whatever you write at the time of configuration).
If you have any doubt any query please feel free to ask about this task or about anything related to IoT.
Just give us a chance to open door of internet of things technology for your smart future.

Just Stay connected with Opencorner.io 






