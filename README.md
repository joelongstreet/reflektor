## Setup
* Install graphics magick
* Install opencv
* Install node
* `npm install`


## Jobs
Create Missing Partner Data:
```javascript
NODE_TLS_REJECT_UNAUTHORIZED=0 node
var jobs = require('./libs/jobs');
jobs.createMissingPartnerData();
```


## Todo

### Photo Collector
x When a plane is broken
x Take a picture using the usb webcam
x Save the image to disk
x Look for faces in the picture and determine certainty
5. Write a record in the photo queue collection
   stating location certainty, and best guess
x If certain, drop photo in correct faces dir

### Barkley Partner Parser
* Visit JunkDrawer's Partner Info page
* Parse the page and look for all the names
* Store the name, id, and picture in a new mongo record
* Look for a face in the photo
* Crop it to face dimensions
* Store it in the faces dir with it's mongo record
* use crypto to generate hash

### Face Verifier
1. Get a record from the photoqueue
2. Display, the image with the computer's best guess (contained in queue record)
3. User can verify, say it's someone else, or say it's nobody that works here

### Display
1. On startup, generate the .csv
2. Camera detects people walking by
3. Compares the video stream to it's local photo db
4. If match is found, pull down user record
5. Read aloud and display...


## Compiling the C++ application
```
  g++ face-recognizer.cpp -o face-recognizer `pkg-config --cflags --libs opencv`
```
