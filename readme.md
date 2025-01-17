# Multi Party Video Call Application using Python (Django) and EnableX Video SDK for Web Browser

Experience a Sample Web App Showcasing EnableX Platform APIs for Building Multi-Party RTC Applications

Dive into an educational journey with this sample web application that showcases the prowess of EnableX platform APIs in crafting fundamental multi-party RTC (Real-Time Communication) applications. The primary objective of this application is to offer developers an immersive experience, allowing them to swiftly acquire app development skills by running it on their own devices instead of relying directly on servers.

Notably, RTC applications hosted on the EnableX platform inherently support a range of web browsers without necessitating any additional plugin downloads. 

This essential multi-party RTC application is ingeniously designed using HTML, CSS, Bootstrap, JavaScript, jQuery, Python, and EnxRtc (The EnableX Web Toolkit), offering a comprehensive demonstration of the EnableX platform's capabilities for seamless real-time communication.

> The details of the supported set of web browsers can be found here:
> https://developer.enablex.io/video/browser-compatibility-of-enablex-video/


## 1. Important!

When developing a Client Application with EnxRtc.js, make sure to include the updated EnxRtc.js polyfills from https://developer.enablex.io/docs/references/sdks/video-sdk/web-sdk/index/ for RTCPeerConnection and getUserMedia. Otherwise your application will not work in web browsers.


## 2. Trial

Sign up for a free trial [https://www.enablex.io/free-trial/](https://www.enablex.io/free-trial/ ) or try our multiparty video chat https://try.enablex.io/.


## 3. Installation

### 3.1 Pre-Requisites

#### 3.1.1 App Id and App Key

* Register with EnableX [https://www.enablex.io/free-trial/ ](https://www.enablex.io/free-trial/ )
* Create your Application
* Get your App ID and App Key
* Clone this Repository `git clone https://github.com/EnableX/Group-Video-Chat-Opensource-Application-in-Python.git` & follow the steps further 
* You can copy the app into any sub-directory of hosted Website on Apache

#### 3.1.2 SSL Certificates

The Application needs to run on https. So, you need to use a valid SSL Certificate for your Domain and point your application to use them. 

However you may use self-signed Certificate to run this application locally. There are many Web Sites to get a Self-Signed Certificate generated for you, Google it. Few among them are:

* https://letsencrypt.org/
* https://www.sslchecker.com/csr/self_signed
* https://www.akadia.com/services/ssh_test_certificate.html  

As you have Certificate or created a Self-Signed Certificate, create a directory "certs" under your Sample Web App Directory. Copy your Certificate files (.key and .crt files)  to this directory.

#### 3.1.3 Configure

Before you run this application, you need to customize  main app `settings.py` file to meet project requirement:

```python
  ENABLEX_API_URL = "https://api.enablex.io/v1"
  ENABLEX_APP_ID = "YOUR_APP_ID"
  ENABLEX_APP_KEY = "YOUR_APP_KEY"
```

### 3.2 Test

* Open a browser and go to [https://yourdomain.com:4443/path-to-sample-app/client/](https://yourdomain.com:4443/path-to-sample-app/client/). The browser should load the App. 
* Allow access to Camera and Mic as and when prompted to start your first RTC Call through EnableX
* You need to Room ID to join. We have added a "Create Room" link below the login form. Click it to get a Room-Id prefilled in the form. 
* You can share the Room-ID with anyone to join your Conference.


## 4. Server API

EnableX Server API is a Rest API service meant to be called from Partners' Application Server to provision video enabled
meeting rooms. API Access is given to each Application through the assigned App ID and App Key. So, the App ID and App Key
are to be used as Username and Password respectively to pass as HTTP Basic Authentication header to access Server API.

For this application, the following Server API calls are used:
* https://developer.enablex.io/docs/references/apis/video-api/content/api-routes/#create-a-room To create room to carry out a video session
* https://developer.enablex.io/docs/references/apis/video-api/content/api-routes/#create-a-token - To create Token for the given Room to join a session

To know more about Server API, go to:
https://developer.enablex.io/docs/references/apis/video-api/index/

## 5. Client API

Client End Point Application uses Web Toolkit EnxRtc.js to communicate with EnableX Servers to initiate and manage RTC Communications.

To know more about Client API, go to:
https://developer.enablex.io/docs/references/sdks/video-sdk/web-sdk/index/
