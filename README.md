# Watson-IoT
How to connect your Arduino to the Watson IoT platform?

## What is Watson IoT
Watson IoT is a powerful service where you can display your data from your device online, from whatson IoT you can export your to Watson data platform were you can feed this data to an AI. In this README we are gonna focus how you can sent your data from an Arduino to the Watson IoT platform.

### Requirements
- NodeMcu
- Lightsensor



## Step 1 Make an account at IBM Cloud 
First we gonna make an account at IBM cloud, this is a service were u can use many API's such as AI and ofcoure the Watson IoT platform.
- Go to https://www.ibm.com/cloud/

- Click add the sign up button

![Form](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/personal-details.png)

- Fill in the form with your personal details

- Confirm the mail from your mailbox 


- After you have confirmed your email and accepted the privacy statement you have to see this screen
![home](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/home-cloud.png)

## Step 2 Create an IBM Watson IoT dashboard 
Now we gonna make a dashboard for our IoT Watson application.

- Go to dashboards in the pancake menu
![menu](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/items.png)

- Click on create a resource  

![IoT](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/menu-cloud.png)


- Search for "internet of things platform" because we wanna connect our IoT device

![platform](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/IOT-platform.png)


- Select the free version because this is good for now

- Click on create 

- If everything goes well you then you have to see the screen right below otherwise make sure that the organisation is your emailadress and "choose a space" is on dev.

![IoT-start](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/IoT-start.png)


## Step 3 Add a new device to the Watson IoT platform
- Welcome to the Watson IoT platform now we gonna select a device for 
- Go to the menu and click on add device.
- ![Add-device-button](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/Add-device-button.png)
- After you get 2 chooses, choose "create device type" 
- Choose a name whatever you want for your device 
- Write in the description what arduino you got for exameple ESP 8266 NodeMcu and go to the next page
- Write as model Node MCU and click next
- Skip the meta data and click on create 
- After this choose your device which you had created and click next
- ![Choose-device](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/choose-device.png)
- Create a device ID and call this whatever you want
- Click on nect till you are on the summary 
- Control if everything is correct and click on create
- VERY IMPORTANT Now you get your device credentials store this save for example in a word document
- ![Device-cred](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/device-cred.png)

- If everything is correct  you have to get the screen like right below this sentences. 
![End-3](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/end-3.png)

- If you don't get this state try to add a device again and check your description from your NodeMcu. The warning sign means that the device is not connected, but we gonna fix that at step 4.

## Step 4 Connect the Arduino 
We are gonna connect the NodeMcu with the IoT Watson platform. 

- Go to this URL https://github.com/t2t-sonbui/IBM-Watson-Internet-of-Things-Tutorial/blob/master/esp8266code/esp8266code.ino
- Copy paste the code in the Arduino editor, if you don't have the Arduino editor installed you can download him here https://www.arduino.cc/en/Main/Software

- Make a new sketch and delete every code in the sketch, after that copy paste the code from github in the editor.

- Now we are gonna customize the wifi code "ssid" means your wifi network, and "password" means the password of the wifi network. 
- ![Cust-wifi](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/wifi-cust.png)

- We are gonne change the default credentials, you have received at the end of step 3. Put your information in between the quotation marks.

- ![Cust-wifi](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/define.png)

so #define ORG "ic01na" will be #define ORG "your organisation number"
#define DEVICE_TYPE "NodeMcu" will be #define DEVICE_TYPE "your device type"
#define DEVICE_ID "demoDevice" will be #define DEVICE_ID "your device ID"
#define TOKEN "JZp5ytS*_)H!tZf*EM" will be #define DEVICE_ID "your device ID"



If you don't have these credentials anymore then you unfortunately have to do step 3 all over again.


- Now we are gonna install the libraries which are needed for the Arduino, otherwise you get a error while you wanna upload the code to the nodeMcu go to sketch -> include library -> manage libraries

- ![lib](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/libraries.png) I have already installed the librarie that is why I cant install him.

- Now we gonna search for PubSubClient

- ![man-lib](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/pubsub.png)

- Choose the latest version and click on install

- Do the same with the librarie ArduinoJson

- Now we are gonna connect an lightsensor to the Arduino as right below.
![man-lib](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/Arduino-sketch.png)

- Now we are gonna upload our code to the Arduino.

- Open the serial monitor on 9600

- If you see this everything goes well the data will be send to IBM Watson and the serial monitor will look like as right below.
![man-lib](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/data-goed.png)


- If you see something like the example below the Arduino can't connect to the network try your hotspot instead.
![false-hots](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/dots.png)

- If the serial monitor looks like this then there is something wrong with your credentials
![false-cred](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/false-cred.png)

- You can see that the data will be received at the IBM Watson IoT platform diveces -> Logs and you will see data coming in. 
![false-hots](https://raw.githubusercontent.com/bjornkouw001/Watson-IoT/master/logs.png)


## Step 5 data visualisation

## Step 6 Connect the database


