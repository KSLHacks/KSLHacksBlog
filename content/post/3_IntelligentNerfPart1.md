---
title: "Intelligent Nerf Turret Part I: The Idea"
date: 2017-05-31
thumbnailImagePosition: left
thumbnailImage: /img/posts/3_thumbnail.png
coverImage: /img/posts/3_coverimage.png
coverMeta: in
coverSize: partial
coverHeight: 40
categories:
- tech
- hardware
- cognitive services
tags:
- Microsoft Cognitive Services
- Raspberry Pi 3
- Arduino
- Servo
- 3D Printing
- Nerf Mod
draft:          false
comments:       true
showTags:       true
showPagination: true
showSocial:     true
showDate:       true
---

First in the series of building an intelligent nerf turret powered with Microsoft Cognitive Services to recognize, classify, swivel and shoot!

<!--more-->
<!--
Notes:
ThumbnailImage dimensions: 700px x 700px
CoverImage dimensions: 1800px x 450px
-->
## The Goal
Create a device that will be able to receive and understand voice commands sent though the computer to target specific items around the room. The device will be mounted on a base with a platform that rotates 360 degrees. When the specified item is found, recognized and identified as a target, the nerf turret will shoot a foam dart. The only input the device should receive is the voice commands, no controller will be used to swivel and aim.
___
## Hardware
- Raspberry Pi 3
- Raspberry Pi  Camera
- Arduino UNO
- (2) Servo Motors
- External power supply for motors
- Nerf (electric)
- 3D Printed Base Mount

___
## Main Parts and Tasks
This is a overview of main tasks that need to be accomplished and tackled. I plan to have dedicated blog posts for each of these tasks so you can understand and learn with us.
### Raspberry Pi
The RP3 will house the logic for this device. The RP3 is responsible for executing the logic that will control the camera, triggering the Nerf turret and communicating with the Arduino to rotate the platform. We will be using Node.js to code this project.

#### Image Recognition
The Raspberry Pi camera will continuously capture images that will be sent to Microsoft's Custom Vision Service to help identify if there are any items in the camera's vision that is of interest to us. Microsoft's CVS provides a great way to train a custom vision model by uploading training images and appropriately tagging them. (such as a cup, soda can or bottle). As we upload new images to the trained model, the service will pass back a prediction JSON with confidence scores associated with each item. If the item is identified in the image with a certain confidence score, such as 0.80 or higher, we know the Nerf turret is aiming at the target.

Start playing around with [Microsoft Custom Vision Service](https://azure.microsoft.com/en-us/services/cognitive-services/custom-vision-service/) for free now! We will be talking more about this in future posts.

#### Nerf
We will be modifying the Nerf's turret trigger mechanism so we will be able to shoot a dart controlled by the Raspberry Pi. The trigger logic will be implemented with the image recognition to determine if the captured image is classified as the correct target.

### Base and Platform
These two 3D printed pieces will be the foundation to house and hold all the electronic components. The base and platform will be two **separate** units which will allow for the device to rotate 360 degrees continuously without worrying about wires. (See image at bottom for reference)

**Base**: The base will be a circular disk, large enough to provide stability to the device, with raised walls. The inside walls will have teeth to allow gears (from the servos) to gain traction and rotate the upper platform. In the center of the base, there will be a raised cylinder structure which will house a ball bearing. This ball bearing will allow the platform, sitting on top of the base, to spin smoothly with minimal friction. The base has three main functions: provide stability to the entire device, provide gear teeth along the inner wall, and house the ball bearing.

**Platform**: The platform will be a disk with the same diameter as the base and must hold all of the electronics and hardware for the device. Below the platform disk, there will be an electronics compartment to house the RP3, Ardiuno UNO, two servo motors and power supply. The servo motors will sit vertically below the platform with gears attached to their axles. The gears will line up with the gear teeth on the base walls to provide the mechanism for the platform to spin as the servos are powered.

On top of the platform disk, there will be a mount for the Nerf as well as the Raspberry Pi camera pointed in-line with the Nerf sights so the device's image will correspond with the Nerf's aim.

The exact dimensions and STL files will be available and explained in a future dedicated post!

### Ardiuno and Servo Motors
Since we have decided to use Node.js as the primary technology for this project, we will be utilizing the [Johnny-Five](http://johnny-five.io/) platform to control the Ardiuno from the RP3. As the RP3 captures images of the surroundings it will consult with the CVS model to identify objects. The servos will continue to rotate the platform until it finds a target.

Two servos attached with gears will be used to rotate the platform.

Rough outline and drawings during our initial white board session (don't judge..)
![diagram](/img/posts/3_platformDiagram.png)

___
This project is in collaboration with [@NoWaySheCodes](https://twitter.com/nowayshecodes) and [@Howlowck](https://twitter.com/howlowck). View our progress on [GitHub](https://github.com/KSLHacks/intelligentNerfTurret) and follow me on Twitter - [@KSLHacks](https://twitter.com/kslhacks) for updates, photos and more blogs!