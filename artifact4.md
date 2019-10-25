## Nicole Beller: GAM-495 Capstone 

![Bandit Ready](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_.jpg?raw=true "Bandit's Question")

### Refined Artifact #4 - *Bandit's Endeavour*

### **Tools Used**
 - Adobe Animate 2018
 - Adobe Flash Player 14
 - ActionScript 3.0
 - Various audio from Freesound.org
 
 
 
### **Inclusion**

My ultimate dream is to be a video game writer. I had learned long ago that video game companies rarely hire video game writers and that they usually want someone who can do more than just write, like program or 3D model. While I enjoy programming, I do love entertaining people through dialogue and world lore. I felt like all of my artifacts had already shown that I can program or proved my ability to be a game designer but nothing showed off my storytelling, until this animation.

When I made this animation, I hoped people would laugh at the ridiculous names I gave the cats and laugh at the fact that I made the main character, the sole boy character, dress up like a princess. I didn’t notice the dark tone hidden within my animation until I returned to it, over a year later. I had completely forgotten that I purposely edited Bandit’s heart collar to slowly deplete as the story went along, showing that Bandit was starting to lose the will to fight.

![Heart-Empty](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_7.jpg?raw=true "Heart - Empty")

![Heart-Half](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_6.jpg?raw=true "Heart - Half")

![Heart-Full](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_5.jpg?raw=true "Heart - Full")

I feel like I made a Disney short, where the children can see the pretty colors and root for the cat to win his freedom but the parents can get the inappropriate jokes and dark humor, which is exactly why I wanted to add this artifact to my ePortfolio. I feel like it shows I’m well-rounded with my writing and I know when to make a joke and when not to take jokes too far.
 
I also learned later on that Adobe Animate is often used for some animated sitcoms, so if a gaming company was making a game based off of a sitcom, I already have experience with Adobe Animate, which would make me more appealing to them. All of the other artifacts, if there was programming involved, I used C++. For this artifact, I used Adobe’s ActionScript language, which made this artifact more appealing to show off. Here's a code snippet of how I made my music button:

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
Additionally, there is one sequence that I was extremely proud of being able to animate: 

![Bandit's GIF](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour.gif?raw=true "Bandit and Shilosh Escaping")

I knew going in that making people walk would be hard to animate, thanks to all of the YouTube clips I watched, but I wanted to at least attempt having my characters walk in some way.  After animating the beginning, having Bandit move from room to room, I realized that it was going to be difficult to add an actual walking sequence, so I came up with a jumping sequence.  I think it came out extremely well, which is why I love this GIF and wanted to showcase this artifact in my ePortfolio.

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

 Returning to this artifact was more daunting than the others because I only ever used Adobe Animate when working on this assignment, so it had been years since I last used this program; the programming language was foreign to me.  I also remembered that one small change in one of the layers could negatively affect the rest of the animation, adding more time to fixing and adjusting instead of adding or changing things.
 
Thankfully, I knew what I wanted to do before I started working on this animation.  The first thing I did was remove nearly all of the buttons.  I understand that my animation was supposed to be interactive but I was never able to find a good interactive animation online to use as an example, so I hated the buttons I was forced to add.  By removing the buttons, the story can flow better and the people watching the animation can sit back and enjoy it instead of having to work for it.  


![Shiloh](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_2.jpg?raw=true "Shiloh")

Another thing I wanted to change was the story.  I felt like I did a rush job in the end, so I wanted to delete and refine some of the dialogue.  

The biggest challenge I ran into while working on this animation was the fact that the animation wouldn’t work properly on my Windows desktop but was fine on my Mac laptop.  When using my desktop, the animation would automatically play at the beginning and the audio would trigger too early and it was just an absolute mess.  My laptop played everything correctly.  I’m not sure if there’s a reason for that, but I felt like it limited how often I could work on the artifact because I share my laptop.  


![Kisses](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_3.jpg?raw=true "Kisses")

I also ran into an issue with the opening sequence.  To animate my cats running across the screen, I made multiple timelines and each time a new timeline began some of the text would apparently move.  To remedy this issue, I would go from timeline to timeline and analyze when and where they moved.  I would rearrange the text accordingly but every time I’d go to ‘Test Video’, the text would still move.  I eventually realized I could zoom in on the canvas and discovered that my text was only off by 0.85.  After checking all of my text locations and changing them to match, everything stopped moving.

![CCL](https://github.com/NicBee/NicBee.github.io/blob/master/Bandits_Endeavour_4.jpg?raw=true "CCL")

Ultimately, I learned that it’s always best to have a copy of your work.  For this artifact, I only had my completed artifact to work on.  I didn’t have any of my milestones or any of my write-ups for my project, which left me feeling a little like a fish out of water.  It was hard to sit down and figure out a plan of attack when there was just so much I wanted to do.

### Return

Click here to return to the main page: [Home](/index.md)
