---
title: "Text Arch"
date: 2022-10-17T21:39:29+08:00
tags: ["Arch-Text","Text"]
categories: ["Obsidian","Excalidraw"]
showToc: false
TocOpen: true
# author: Brandon Janssen
draft: false
hidemeta: false
comments: false
#description: "A "
# canonicalURL: "https://github.com/zsviczian/obsidian-excalidraw-plugin"
disableHLJS: true # to disable highlightjs
disableShare: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
ShowRss: true
UseHugoToc: true
cover:
    image: "img/banner.png" # image path/url
   # alt: "Tetu" # alt text
    # caption: "Fusion operates on the NovaNetwork and Fantom Network" # display caption under cover
    #relative: false # when using page bundles set this to true
    hidden: false # on
---

# Text To Arch Script With Excalidraw On Obsidian
![](https://imgur.com/I8c05jw.png)

First we need to install excalidraw on obsidian. This is the link for [Excalidraw GitHub](https://github.com/zsviczian/obsidian-excalidraw-plugin) and it  will show quite a bit of info, but you will want to install it from community plugins page in setting and you will have to turn on restricted mode. 

---
![Text](https://imgur.com/uV1pgOk.png "Title")   

In the top right button that looks like settings icon click that and it will bring up all the scripts available to install, the text arch script was close to the bottom of the page. 

After that is done we have to figure out how to use it, if you are like me and pretty new to excalidraw it can take a little time to sort out all the features it has to offer.



---
Now you will want to write some text, make sure the text is in a expandable box. Then at top right click the obsidian icon, a drop down menu will appear and there will be a section that says ***Downloaded Scripts***. Next click the text arch icon then follow the instructions.

![](https://imgur.com/vfPAUYQ.png)


After messing around with it for a few minutes you can achieve something like this, or something  much much better.

![](https://imgur.com/3Q0Xbp6.png)




---
Excalidraw is an exceptional add on to obsidian and has helped me several times in my short knowing of this tool. This tool fits so many needs, drawing, flow charts, mind maps, and much more, add in scripting and the possibilities are endless. Want to know more, this is his youtube channel  [Zsolt's Visual Personal Knowledge Management](https://www.youtube.com/c/VisualPKM), his videos are quite lengthy sometimes but detailed.


---
> This is the script that will be installed on obsidian and  can be found [here.](https://github.com/zsviczian/obsidian-excalidraw-plugin/blob/master/ea-scripts/Text%20Arch.md)
>
> This script is viewable and editable on obsidian. 

```
*/
el = ea.getViewSelectedElement();
if(!el || el.type!=="text") {
	new Notice("Please select a text element");
  return;
}

ea.style.fontSize = el.fontSize;
ea.style.fontFamily = el.fontFamily;
ea.style.strokeColor = el.strokeColor;
ea.style.opacity = el.opacity;

const r = parseInt (await utils.inputPrompt("The radius of the arch you'd like to fit the text to","number","150"));
const archAbove = await utils.suggester(["Arch above","Arch below"],[true,false]);

if(isNaN(r)) {
  new Notice("The radius is not a number");
  return;
}

circlePoint = (angle) => archAbove
  ? [
		r * Math.sin(angle),
		-r * Math.cos(angle)
	]
	: [
		-r * Math.sin(angle),
		r * Math.cos(angle)
	];

let rot = (archAbove ? -0.5 : 0.5) * ea.measureText(el.text).width/r;

let objectIDs = [];
for(i=0;i<el.text.length;i++) {
	const character = el.text.substring(i,i+1);
	const width = ea.measureText(character).width;
  ea.style.angle = rot;
  const [x,y] = circlePoint(rot);
  rot += (archAbove ? 1 : -1) *width / r;
  objectIDs.push(ea.addText(x,y,character));
}
ea.addToGroup(objectIDs);
ea.addElementsToView(true);

```









