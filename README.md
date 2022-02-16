##Creating a generative art on ESP32 with Arduino



### Description of the project
For this class-scale group project, a series of generative art was displayed on TTGO ESP32. Each of the teammates individually soldered a 500mAh battery to a wire that connects to ESP32, and loaded a text-based art that they created with Arduino.

The devices were then charged for 1-2 hours with a usb-c cable that connects to a laptop, so that it could stay on for 5 hours approximately.

Each of the devices that display the art on their screen were packed in a white cardboard paper, so that it encapsulates them like a box. 
\

The paper had a rectangular cut that fits the screen of ESP32. The devices were packed so that only the screen of the machine is visible to the audience. 

The surface of the boxes was decorated using black ink. A black string was connected to the hole on the box. The other end of the string was connected to a popsicle bar. Using the bar, the devices were hung on the ceiling in a straight line, with varying height. The installation site for this project was an academic hub of a college, on a floor where students take classes in. To be specific, the art was installed at the elevator lounge. 
![IMG_9078](https://user-images.githubusercontent.com/25335750/154197451-a867bb7d-4c7a-4556-a629-a395c2852488.jpg)
![IMG_9080](https://user-images.githubusercontent.com/25335750/154197512-fba3759b-d2a2-431f-8a97-404df6f7ac2b.jpg)



On my device, a generative, visual poem about “rain” was displayed. 

### Creating the art generatively
Visual poems are defined as poem that visualizes its contents. I intended to create a poem with its title representing the cloud, and the stanza representing the raindrops. This was achieved by setting the color of the title white, and the color of the rest of the poem blue. In addition, to visualize the raindrops, only one word was used in each line, and their locations were inconsistent, effectively representing drizzling rain falling in a chaotic manner.

The poem is generative, as the words and their location are chosen by a randomizer code. On Arduino, I created a randomizer function that chooses a word from an array of onomatopoeia that describes rain. With another randomizer function, blank spaces that is to be printed before the onomatopoeia is created. These were created with random(n) function on Arduino, which randomly chooses an integer between 0 and n. To be specific:


/**
 * This function  returns one of the string from the array of onomatopoeia. 
 * It sets spaceLength as (40 - length of chosen onomatopoeia). 
 * Note that 40 was used because 40 characters fits the in one line for screen size of 160 * 128, when font size is 1
 * 
 * @param randomNumber the random number created to choose which word to return from the array of onomatopoeia.
 * @return onomatopoeia the string of onomatopoeia
 */
char* createWords(int randomNumber){
    if(randomNumber == 0){
      spaceLength = 35;
     return onomatopoeia[0]; 
    }
    if(randomNumber == 1){
         spaceLength = 35;
         return onomatopoeia[1];  
    }
    if(randomNumber == 2){
      spaceLength = 34;
          return onomatopoeia[2]; 
    }
    if(randomNumber == 3){
       spaceLength = 34;
         return onomatopoeia[3];  
    }
    if(randomNumber == 4){
       spaceLength = 36;
            return onomatopoeia[4];  
    }
    if(randomNumber == 5){
       spaceLength = 33;
            return onomatopoeia[5];  
    }
    if(randomNumber == 6){
       spaceLength = 33;
           return onomatopoeia[6]; 
    }
     if(randomNumber == 7){
           spaceLength = 40;
           return onomatopoeia[7]; 
    }
       
}

/**
 * This function returns empty space, the length of the space is determined randomly.
 * Using random(maxLen), it creates a number from 0 to maxLen, which was then used in for loop to add empty spaces.
 * 
 * @param maxLen the maximum length of the empty string
 * @return str the string of empty spaces
 * 
 */
String createSpace(int maxLen){
  String str = "";
  int randomNumber = random(maxLen);
  for(int i = 0; i < randomNumber; i++) {
        str += " ";  
    }
    return str;
  
}
  

Above are part of the code written on arduino. The full code can be found on:
https://github.com/ChangSuNam/-generative-art/blob/main/Module1_poem.ino

After these were written, one can connect TTGO ESP32 to the laptop with a usb-c cable and press "upload" on Arduino to update the code on to the device.


Since the theme of my poem is rain, I decorated the cardboard package with a drawing of cloud and rain falling from it. On the back of the box where the screen is invisible, I drew the raindrops with ink, but on the front where the screen is visible, I simply drew the cloud above the screen, so that the words on the screen can remind the audience of raindrops. When installing this art, I spun the machine so that over time it slowly turns around. The audience could see both side of the box this way.



The target audience of this art is students and staff of the college where it was installed. I decided to create a generative visual poem about rain because I wanted to display something about nature, which the target audiences tend to forget about working indoors most of their time.

Issue I encountered during this project was trying to load the text to ESP32. Most of the teammates had similar issue with this. Some of us had to get a new device, and some of us could fix this issue by importing the library again on Arduino. It was also hard to figure out how many lines and characters fit on the screen. By trial and error, I found out that 40 characters fit in one line when the font size is 1, and 16 lines of this can fit on ESP32 with screen size 160*128


###Video illustrating how the arts were installed:
https://user-images.githubusercontent.com/25335750/154197673-c30400e9-0b09-4865-bce9-b690a88f40b4.MOV


