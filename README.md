# -AR---AI-Cut-Paste-
AR Cut & Paste
An AR+ML prototype that allows cutting elements from your surroundings and pasting them in an image editing software.

Although only Photoshop is being handled currently, it may handle different outputs in the future.

Demo & more infos: Thread

⚠️ This is a research prototype and not a consumer / photoshop user tool.

Modules
This prototype runs as 3 independent modules:

The mobile app

Check out the /app folder for instructions on how to deploy the app to your mobile.
The local server

The interface between the mobile app and Photoshop.
It finds the position pointed on screen by the camera using screenpoint
Check out the /server folder for instructions on configuring the local server
The object detection / background removal service

For now, the salience detection and background removal are delegated to an external service
It would be a lot simpler to use something like DeepLap directly within the mobile app. But that hasn't been implemented in this repo yet.
Usage
1 - Configure Photoshop
Go to "Preferences > Plug-ins", enable "Remote Connection" and set a friendly password that you'll need later.
2 - Setup the external salience object detection service
As mentioned above, for the time being, you must deploy the BASNet model (Qin & al, CVPR 2019) as an external HTTP service using this BASNet-HTTP wrapper (requires a CUDA GPU)

You will need the deployed service URL to configure the local server

3 - Configure and run the local server
Follow the instructions in /server to setup & run the local server.
4 - Configure and run the mobile app
Follow the instructions in /app to setup & deploy the mobile app.
Thanks and Acknowledgements
BASNet code for 'BASNet: Boundary-Aware Salient Object Detection code', Xuebin Qin, Zichen Zhang, Chenyang Huang, Chao Gao, Masood Dehghan and Martin Jagersand
RunwayML for the Photoshop paste code


# AR Cut Paste Mobile App

A [React Native](#) mobile application.

## Setup

```bash
npm install
```

Then update the IP address in `components/Server.txt` to point to the IP address of the computer running the local server:
```js
3: const URL = "http://192.168.1.29:8080";
```

## Run

```bash
npm start
```

