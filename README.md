# Shredder-Machine
In this i have made a hand detection model which can detect the live feed through the camera and can detect the hand movements and if the hand goes into the danger region we can stop the machine then and there.

# Problem Statement
As many of us may have come across the accidents in the newspapers about the shredder-machine that several workers got their hands chopped off due to carelessness or whatever may be the reason.
This is why i took this problem and tried to built a solution for it.
Those who do not know what is a shredder-machine just find the images attached below:-

![](https://github.com/anubhav6864/Shredder-Machine/blob/main/utils/shredder1.jpeg) 
![](https://github.com/anubhav6864/Shredder-Machine/blob/main/utils/shredder2.jpeg) 

# Solution
I have designed an AI solution using the Computer Vision which includes the following functionality:-

--> I am collecting the live feed from the cameras installed it can be any camera, we just need to configure it in our code using the RTSP protocol (using OpenCV)
--> Built a hand detection model to detect hands in the frame captured by the live feed from the camera.
    -experimented with several models like Faster RCNNs, SSDs but at last i selected SSD lite model as it was giving good performance on hand detection as well as        good processing speed. 
    -I have set the threshold of 0.8 i.e if the confidence score is above 80% then only we will be able to call it as correct detection and then only our machine        will act accordingly
    -It will detect any no. of hands be it 1 to whatever no. of hands present in the frame.
--> Collected good no. of images of the hands variations and then performed the data augmentation on top of it to make it more robust more every possible lighting condition.
--> Labelled the images with two classes i.e 
1. Closed hand(fist) as Gloved Hand 
2. Normal Hand image

--> Then i created two border lines with respect to the frame with the help of distance formula that we were capturing.
1. Safety Border line (Which will give us the alert alarm if our hand passes that line)
2. Machine Borderline, if the hand is close to it then our code will pass a signal to the shredder-machine and it will switch off automatically in order to avoid any accident.
3. With respect to that lines i am also calculating the distance of the hand from these lines.

Here is the demo image:-

![](https://github.com/anubhav6864/Shredder-Machine/blob/main/utils/demo.png) 

In order to run this project in your local system clone this repo and install all the requirements and if you like please do share your feedback to me over my linkenin mentioned on my github homepage.


