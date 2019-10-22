## Nicole Beller: GAM-495 Capstone 

![Bandit Ready](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_.jpg?raw=true "Bandit's Question")

### Refined Artifact #4 - *Bandit's Endeavour*

### **Tools Used**
 - Adobe Animate 2018
 - Adobe Flash Player 14
 - ActionScript 3.0
 - Various audio from Freesound.org
 
 
 
### **Inclusion**
![Heart-Empty](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_7.jpg?raw=true "Heart - Empty")

![Heart-Half](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_6.jpg?raw=true "Heart - Half")

![Heart-Full](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_5.jpg?raw=true "Heart - Full")

```markdown
/* Click to Play/Stop Sound
Clicking on the symbol instance plays the specified sound.
Clicking on the symbol instance a second time stops the sound. */

Music.addEventListener(MouseEvent.CLICK, fl_ClickToPlayStopSound_2);

var fl_SC_2:SoundChannel;

//This variable keeps track of whether you want to play or stop the sound
var fl_ToPlay_2:Boolean = true;

function fl_ClickToPlayStopSound_2(evt:MouseEvent):void
{
	if(fl_ToPlay_2)
	{
		var s:Sound = new NewMusic();
		fl_SC_2 = s.play();
	}
	else
	{
		fl_SC_2.stop();
	}
	fl_ToPlay_2 = !fl_ToPlay_2;
}
```

![Bandit's GIF](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour.gif?raw=true "Bandit and Shilosh Escaping")



### **Skills Learned**
  - Employ effective foundational technologies in the development of creative interactive animation
  - Create original elements by applying appropriate technical aspects of interactive animation including sound and video
  - Create efficient user experiences that employ interactive navigation
  - Analyze the implications of different scripting tools for selecting the most effective platform
  - Identify the capabilities of programming scripts for optimizing the interactive user experience
  
 ### **Highlighted Skills**
  - 2D Graphics: showcases how I was able to make a simple story with only 2D models; my characters don't stand still and are animated like a cartoon.
  - Graphic Interface Design: showcases that I can make an animation that looks well-put-together and the scenes flow together effortlessly
  - Narration & Story: showcases that I can create simple but meaningful stories with appealing characters; I also have an eye for graphic design, like Bandit's heart necklace that quietly changes throughout the narration
  
  
### **Revised Components**
- 2D Graphics
- Graphic Interface Design
- Narration & Story
  
### **Reflection**

![Bandit's Endeavour](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_1.jpg?raw=true "Bandit's Endeavour")

![Shiloh](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_2.jpg?raw=true "Shiloh")

![Kisses](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_3.jpg?raw=true "Kisses")

![CCL](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_4.jpg?raw=true "CCL")

### Return

Click here to return to the main page: [Home](/index.md)
