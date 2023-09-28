# Report 5 - Week of 09/21/2023 (Week 5)
## Junyan Du (Jenny), Technology Design Foundations

### Summary: 

This week I furthered explored Photon, downloaded VS Code and setting up to have corresponding output in Serial Monitor. 

[![TDF Video](https://i3.ytimg.com/vi/YVCr87Oi7vk/maxresdefault.jpg)](https://youtu.be/YVCr87Oi7vk "Documentation Video")
(Click on the link to watch in Youtube)

### Reflections:

During our in-class workshop, Jeff taught us how to set up VS code and provided a code to have the characters "HELLO WORLD" printed out in the serial monitor corresponding to the LED light blinks. 

<img width="80%" src="weekly-reports/Week 5/board1.jpg">

Here is the code:

```
const pin_t MY_LED = D7;
char str[12] = "HELLO WORLD";

int counter = 0;

void setup()
{
    Serial.begin(9600);
	pinMode(MY_LED, OUTPUT);
}

void loop()
{
	digitalWrite(MY_LED, HIGH);
	delay(500);
	digitalWrite(MY_LED, LOW);
	delay(500);
	Serial.printf("the character:%c\n", str[counter]);
	counter++;
	if(counter>11){
	    counter=0;
	}
	delay(1000);
}
```
And here is the result:

<img width="80%" src="weekly-reports/Week 5/Lightslow.gif">

I found it blinking too slow, so I adjusted the delay time to "500" (0.5s), and then try output it with the phrase "LIGHTS ON" instead of "HELLO WORLD".

Here is the code:

```
const pin_t MY_LED = D7;
char str[10] = "LIGHTS ON";

int counter = 0;

void setup()
{
    Serial.begin(9600);
	pinMode(MY_LED, OUTPUT);
}

void loop()
{
	digitalWrite(MY_LED, HIGH);
	delay(500);
	digitalWrite(MY_LED, LOW);
	delay(500);
	Serial.printf("the character:%c\n", str[counter]);
	counter++;
	if(counter>9){
	    counter=0;
	}
	delay(500);
}
```
Here is how the characters are printed out (2x the speed then the previous code):

<img width="80%" src="weekly-reports/Week 5/lightson.gif">


### Speculations:

It was fun exploring photon and how it can be connected to the Serial Monitor for outputs related to the LED Light. I look forward to further explorations!



---
---

# Report 4 - Week of 09/14/2023 (Week 4)
## Junyan Du (Jenny), Technology Design Foundations

### Summary: 

This week I first finished the Project PDF for Project 1: Computational Design. In this PDF I mainly introduced my project, the process of making it, challenges I faced, speculations regarding computational design, and reflections on the feedback I received in class. 

I also started setting up for our next project: Photon / Physical computation, and I am very excited about it!

### Reflections:

Here are the steps I followed to set up for Photon:

First is the initial set up:

<p float="left">
  <img src="weekly-reports/Week 4/01_setup.png" width="45%" />
  <img src="weekly-reports/Week 4/01_done.png" width="45%" /> 
</p>

Next is the Configure Wi-Fi:

<img width="80%" src="weekly-reports/Week 4/02_wifi.png">

Then getting Mac Address:

<p float="left">
  <img src="weekly-reports/Week 4/03_address.png" width="45%" />
  <img src="weekly-reports/Week 3/03_address2.png" width="45%" /> 
</p>

Last step for now is the add the device in Berkeley IoT Wifi:

<img width="80%" src="weekly-reports/Week 4/04_IoT.png">


### Speculations:

I am very excited to learn and explore physical computing.



---
---

# Report 3 - Week of 09/07/2023 (Week 3)
## Junyan Du (Jenny), Technology Design Foundations

### Summary: 

This week I further explored what I can do with Rhino and Grasshopper, and I did a "Desk Basket" for a fun activity when I get tired of work. 

<img width="80%" src="weekly-reports/Week 3/FinalGIF.gif">

I created a bracelet and explored the Voronoi Patter in Grasshopper. 

<p float="left">
  <img src="weekly-reports/Week 3/GH_V+B.png" width="45%" />
  <img src="weekly-reports/Week 3/GH_VC1.png" width="45%" /> 
</p>

Here is a video that documents the whole process of my exploration:

[![TDF Video](https://i3.ytimg.com/vi/Uyn1tSN2wp8/maxresdefault.jpg)](https://youtu.be/Uyn1tSN2wp8 "Documentation Video")

### Reflections:

I started of with doing the Bracelet.

<img width="80%" src="weekly-reports/Week 3/GH_B1.png">
<img width="80%" src="weekly-reports/Week 3/GH_B_G1.png">

The shape of the bracelet is adjustable by simply adjusting different parameters such as the Radius and Segments of the Polygon, as well as the number of frames created alongside the curve. The edge can be more rounded or sharp depends on the Fillet Radius of the Polygon. 

<img width="80%" src="weekly-reports/Week 3/GH_B2.png">

I chose the middle one to do a 3D-print, and here is the outcome: 

<img width="80%" src="weekly-reports/Week 3/Print1.jpg">

Next I worked on exploring the voronoi shape in Grasshopper. I realized that Grasshopper can create very interesting Voronoi Patterns that can be applied to a 3D-object. 

<img width="80%" src="weekly-reports/Week 3/GH_V1.png">
<img width="80%" src="weekly-reports/Week 3/GH_V_G1.png">

The different thickness can be adjusted regarding how much of a scale-down on each cell is conducted:

<img width="80%" src="weekly-reports/Week 3/GH_V_G2.png">

I also trimed the top and adjusted the size to have the Voronoi shaped "Basket" fit the Bracelet.

<img width="80%" src="weekly-reports/Week 3/GH_V3.png">

Here is the 3D print:

<p float="left">
  <img src="weekly-reports/Week 3/Print3.JPG" width="45%" />
  <img src="weekly-reports/Week 3/Print4.jpg" width="45%" /> 
</p>

I continued my exploration about the Voronoi shape, and focused on doing color coding with the shape.

<img width="70%" src="weekly-reports/Week 3/GH_VC1.png">
<img width="100%" src="weekly-reports/Week 3/GH_VC_G1.png">

By having adding a curve on the flattened sruface, I added more condensed points to populate center points for the Voronoi Cells. That makes the cells close to the curve smaller, and the others larger. Through having a Green-to-blue gradient, the green side is assigned to cells in smaller volume (close to curve), while blue side is asiigned to the ones in larger volume. And the Red one is simpler by having the gradient change vertically along the object. 

<img width="60%" src="weekly-reports/Week 3/VC_Final.jpg">

I figured that Voronoi Pattern has certain limitations on the Surface it is applied to. When the Surface is too curvy or complicated, the extrusion of the Voronoi Pattern might fail to create a closed Polysurface object in Rhino and that cannot go through the 3D Printer. 


### Speculations:

I really enjoyed the process of exploring new features in Grasshopper, especially the Voronoi Pattern. I would like to explore further on using Grasshopper to make interesting patterns that can be applied to 3d shapes/objects. 


---
---


# Report 2 - Week of 08/31/2023 (Week 2)
## Junyan Du (Jenny), Technology Design Foundations

### Summary: 

This week I further explored parametric design by adjusting different parameters in Grasshopper, to produce a final outcome of a Laser-Cut Phone Stand and a 3D-Print Phone Stand. Throughout the process, I get to be more familiar with Grasshopper, and the fabrication tools in Jacobs Makerspace.

Here is the Final Result:

<p float="left">
  <img src="weekly-reports/Week 2/Laser_Final_2.JPG" width="30%" />
</p>

Note: The 3D printing model is still in progress, I'll upodate here when it's finished. 


---

### Reflections:

Since I've measured the phone size last week, this week I first start with measuring the table size and height. Since I found the angle is a little too low from last week when putting the phone stand on my desk. 

<p float="left">
  <img src="weekly-reports/Week 2/Measure1.JPG" width="30%" />
  <img src="weekly-reports/Week 2/Measure2.JPG" width="30%" /> 
  <img src="weekly-reports/Week 2/Measure3.jpg" width="30%" />
</p>

Afterwards, I adjusted the parameters in Grasshopper accordingly. 

<p float="left">
  <img src="weekly-reports/Week 2/G_Process_Parameters.png" width="30%" />
  <img src="weekly-reports/Week 2/G_Process_Parameters_Phone.png" width="35%" /> 
  <img src="weekly-reports/Week 2/G_Process_Parameters_Table.png" width="30%" />
</p>

Then I first start with the laser cutting file, since I've worked with them last week. After baking the curves, I edited it in rhino to have rounded angles. Additionally, since I hope to be prepared for different material thickness, so I outputted two different thicknesses: 4mm and 6mm. 

<p float="left">
  <img src="weekly-reports/Week 2/Laser_Process_R1.png" width="40%" />
  <img src="weekly-reports/Week 2/Laser_Process_R2.png" width="50%" /> 
</p>

Then I export this file into Ai to add more customizing features to it. I added my name as a rester, and added some cute curves:)

<img width="50%" src="weekly-reports/Week 2/Laser_Process_A0.png">
<img width="50%" src="weekly-reports/Week 2/Laser_Process_A1.png">

The next step is to set up for do Lasercut. I used clear acrylic (1/8in), which is about 3.1mm. In this case, I choose the file with a 4mm thickness setting. However, the piece was too thin and is not very stable after I assembled them. In this case, I printed every piece twice, and found out that doubling up the thickness makes every piece fit together stably. 

<img width="50%" src="weekly-reports/Week 2/Lasercut1.jpg">
<img width="50%" src="weekly-reports/Week 2/Lasercut2.JPG">

Here is the final assembly: 

<p float="left">
  <img src="weekly-reports/Week 2/Laser_Final_2.JPG" width="30%" />
  <img src="weekly-reports/Week 2/Laser_Final_3.jpg" width="30%" /> 
  <img src="weekly-reports/Week 2/Laser_Final_4.jpg" width="30%" />
</p>

Here is a picture showing this week and last week's model side by side:

<img width="60%" src="weekly-reports/Week 2/Laser_Final_6.jpg">

And this is a screenshot of a video I recorded using the phone stand. As you can see, it's in a good angle to film my upper body and my gestures. 

<img width="60%" src="weekly-reports/Week 2/Laser_Final_5.jpg">

---

This week I've also worked on the 3D Model of the Phone Stand and get a chance to print it out using a Makerbot. 
The first step is to bake the "3D Model brep" after adjusting all the parameters to fit my own need. 

<p float="left">
  <img src="weekly-reports/Week 2/G_Process_Bake1.png" width="40%" />
  <img src="weekly-reports/Week 2/G_Process_Bake2.png" width="40%" /> 
</p>

Then in Rhino, I fillet the edges to have it be more rounded and smooth. 

<p float="left">
  <img src="weekly-reports/Week 2/3D_Process_R1.png" width="40%" />
  <img src="weekly-reports/Week 2/3D_Process_R2.png" width="40%" /> 
</p>

<img width="80%" src="weekly-reports/Week 2/3D_Process_R3.png">

Next step is to 3D Print the model. I exported to stl and then slice it to have a gcode file. Then I used the online "3DPrinterOS" website to queue my print for Makerbot 3 at Jacobs Hall. 

<p float="left">
  <img src="weekly-reports/Week 2/3D_Process_STL.png" width="40%" />
  <img src="weekly-reports/Week 2/3D_Process_Slice.png" width="40%" /> 
</p>

<img width="80%" src="weekly-reports/Week 2/3D_Process_Print.png">

And here is the final result of the 3D-print Phone Stand.

Note: The 3D printing model is still in progress, I'll upodate here when it's finished. 

---

### Speculations:

I was very happy with the final outcome, and I get to be more familiar with different software (Grasshopper, Rhino, Ai, UCP) and fabrication skills. The phone stand is more stable this time, with more customized features, and the angle perfectly matches my height and the table height to film myself standing and doing things. 

I look forward to bring these skills I learned and practiced to my own design projects in the future. 


---
---


# Report 1 - Week of 08/24/2023 (Week 1)
## Junyan Du (Jenny), Technology Design Foundations

### Summary: 

This week, through using Rhino and Grasshopper, I utilized TDF Computational Design project files to produce a phone stand for myself to document in the course.
I made adjustments in Grasshopper regarding my phone size, table height, and my height to best fit my usage of this phone stand. Then I export to file to Adobe Illustration and then Laser Cut the file out with Plywood. The final result fits my phone well, and works great filming myself. 

Here is the Final Result:

<p float="left">
  <img src="weekly-reports/Week 1/Final.4.JPG" width="30%" />
  <img src="weekly-reports/Week 1/Final.5.JPG" width="30%" /> 
  <img src="weekly-reports/Week 1/Final.3.jpeg" width="30%" />
</p>

---

### Reflections:

I first Measured the height and width of my phone (with phone case):

<p float="left">
  <img width="45%" src="weekly-reports/Week 1/Measure.1.jpeg" />
  <img width="45%" src="weekly-reports/Week 1/Measure.2.jpeg" /> 
</p>

Next, I adjusted in Grasshopper to have the Phone Size, Table Height, and my Height customized to myself. 

<img width="45%" src="weekly-reports/Week 1/Process.G1.png">

Then Bake the Joined vector:

<img width="45%" src="weekly-reports/Week 1/Process.G2.png">

Here's how it looks in Rhino:

<p float="left">
  <img width="45%" src="weekly-reports/Week 1/Process.R1.png" />
  <img width="45%" src="weekly-reports/Week 1/Process.R2.png" /> 
</p>

Afterwards, I exported the file into Ai and set it to the required file settings for Laser Cut:

<img width="45%" src="weekly-reports/Week 1/Process.A1.png">
<img width="45%" src="weekly-reports/Week 1/Process.A2.png">
<img width="45%" src="weekly-reports/Week 1/Process.1.JPG">

Finally, Put the pieces together and it fits my phone well!

Here is a video I recorded by having the phone on the phone stand:

<p float="left">
  <img width="45%" src="weekly-reports/Week 1/FinalGIF.gif" />
  <img width="45%" src="weekly-reports/Week 1/FinalGIF2.gif" /> 
</p>

I really enjoyed doing this project, and I quite struggled at the beginning since I am not that familiar with Grasshopper. I took me a while to figure out the logic in Grasshopper and how to adjust the measurements. 

---

### Speculations:

It currently fits my phone very will and can clearly film a video in selfie mode. This can be very helpful in documenting in the future. 
I also look forward to my it more suitable for different situations, for example, an adjustable height. 

