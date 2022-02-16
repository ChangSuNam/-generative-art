##Creating a generative art on ESP32 with Arduino



### Description of the project
For this class-scale group project, a series of generative art was displayed on TTGO ESP32. Each of the teammates individually soldered a 500mAh battery to a wire that connects to ESP32, and loaded a text-based art that they created with Arduino.

The devices were then charged for 1-2 hours with a usb-c cable that connects to a laptop, so that it could stay on for 5 hours approximately.

Each of the devices that display the art on their screen were packed in a white cardboard paper, so that it encapsulates them like a box. 
\

The paper had a rectangular cut that fits the screen of ESP32. The devices were packed so that only the screen of the machine is visible to the audience. 

The surface of the boxes was decorated using black ink. A black string was connected to the hole on the box. The other end of the string was connected to a popsicle bar. Using the bar, the devices were hung on the ceiling in a straight line, with varying height. The installation site for this project was an academic hub of a college, on a floor where students take classes in. To be specific, the art was installed at the elevator lounge. 

![IMG_9080](https://user-images.githubusercontent.com/25335750/154197512-fba3759b-d2a2-431f-8a97-404df6f7ac2b.jpg)



On my device, a generative, visual poem about “rain” was displayed. 

### Creating the art generatively
Visual poems are defined as poem that visualizes its contents. I intended to create a poem with its title representing the cloud, and the stanza representing the raindrops. This was achieved by setting the color of the title white, and the color of the rest of the poem blue. In addition, to visualize the raindrops, only one word was used in each line, and their locations were inconsistent, effectively representing drizzling rain falling in a chaotic manner.

The poem is generative, as the words and their location are chosen by a randomizer code. On Arduino, I created a randomizer function that chooses a word from an array of onomatopoeia that describes rain. With another randomizer function, blank spaces that is to be printed before the onomatopoeia is created. These were created with random(n) function on Arduino, which randomly chooses an integer between 0 and n. 

Since the theme of my poem is rain, I decorated the cardboard package with a drawing of cloud and rain falling from it. On the back of the box where the screen is invisible, I drew the raindrops with ink, but on the front where the screen is visible, I simply drew the cloud above the screen, so that the words on the screen can remind the audience of raindrops. When installing this art, I spun the machine so that over time it slowly turns around. The audience could see both side of the box this way.



The target audience of this art is students and staff of the college where it was installed. I decided to create a generative visual poem about rain because I wanted to display something about nature, which the target audiences tend to forget about working indoors most of their time.

Issue I encountered during this project was trying to load the text to ESP32. Most of the teammates had similar issue with this. Some of us had to get a new device, and some of us could fix this issue by importing the library again on Arduino. It was also hard to figure out how many lines and characters fit on the screen. By trial and error, I found out that 40 characters fit in one line when the font size is 1, and 16 lines of this can fit on ESP32 with screen size 160*128


###Video illustrating how the arts were installed:
https://user-images.githubusercontent.com/25335750/154197673-c30400e9-0b09-4865-bce9-b690a88f40b4.MOV


