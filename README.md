# LibrarySeatFinder
Mobile application that performs image recognition on surveillance videos to find seats efficiently in libraries.

# Input
The name of the library and the floor on which the end user wants to study at.

# Components
1. Person Identification Module
2. Interfacing Module
3. Notification Module

# Component Description

1. Person Identification Module:
To detect if a person is occupying a public seat in a library, we need to train a system to classify between occupied and empty seats. We start with extracting the frame at time the request for spot arrives to the mobile app. We analyze the frame and find spots wherein there are no people detected we mark that spot as empty and collect all such spots and form the output.
We detect all "person" objects in the frame(Based on the input floor)and get the coordinates of the block where the person is detected using Tensorflow.

2. Interfacing Module
The empty seats found from the previous module are then fed to a mongoDB database wherein we add the floor number and locations of empty seats.This information can then be conveyed to our mobile application based on the end user’s requirement (which floor he wants to study in).

3. Notification Module
This part of the project would include sending a text message to the user after they have put in a request for the information. User will receive a link in the message from the Library seat finder system which will show the floor layout of the requested floor with availability for seats marked with green box.This is planned to be implemented using Twilio APIs to notify via SMS.

# Output:
Notification with a link to the available seats on the floor requested to study on.






