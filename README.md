# ProjectGotham
#Data Generation
This tool assists with the optical character recognition for Sunwave's mailing technology. It allows the self-driving vehicles and drones to detect texts and read addresses for dropping off packages to the accurate destination.
OCRDrone is a NodeJS application written for a NodeCopter demonstration.

OCRDrone uses the drone's video camera to continuously save camera footage to the filesystem, passing each image to nodecr for text recognition. If the text is recognised as a valid command, it is then translated into flight commands and sent to the drone in real-time.

Demo
You can see a short video of this application being demoed at NodeCopter Southampton. (Skip through to 12:10).

Here is another video of exactly the same demo, created by stitching together all the images captured by this application. This is what OCRDrone sees and processes.

Prerequisites
ar-drone - http://github.com/felixge/node-ar-drone:

npm install ar-drone.
nodecr - http://github.com/joscha/nodecr:

npm install nodecr
The following applications also need to be downloaded and installed on your system. NOTE: the executable binaries of each must be available in your system path.

tesseract: http://code.google.com/p/tesseract-ocr

ffmpeg: http://ffmpeg.org/download.html

Usage
node ocrDrone.js
Tips
Although it is possible to show text to drone's camera using a laptop/tablet, we found that text printed on paper worked much better.

The longer the text/command, the better the match. We found that tesseract preferred "LAND PLEASE" to just "LAND".

It appears that the video stream can only be consumed by one application. So, if you're capturing the onboard video with another application, then you might get TcpVideoStream errors from OCRDrone.

Occasionally, we got TcpVideoStream errors when starting the application. Pressing Ctrl+C and restarting the application a couple of times eventually got it working. Sometimes we had to disconnect/reconnect to the WiFi.
