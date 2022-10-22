---
title: "Text From Image With Python"
date: 2022-10-20T20:15:08+08:00
tags: ["Text-from-Image","Text"]
categories: "Python"
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
    #image: "img/banner.png" # image path/url
   # alt: "Tetu" # alt text
    # caption: "Fusion operates on the NovaNetwork and Fantom Network" # display caption under cover
    #relative: false # when using page bundles set this to true
    hidden: false # on
---

# Copying Text from Image with Python
One of the fastest ways to extract text from a image is with python. The basic script to do this is very small, it can get quite complicated depending on what you are trying to achieve.

I will only show the basics to make this work and this only applies to Linux Debian based systems.

if you like it and want to know more there is plenty of resources to research from.

---
 - We will need PyTesseract
 - And we will need  OpenCV

I will be using VScode to demonstrate all of this. Install these two libraries using the terminal.

## Step 1. Dependencies


```
pip install opencv-python
```
```
pip install pytesseract
```

```
sudo apt update
```
```

sudo apt-get install libtesseract-dev tesseract-ocr  
```

1.  **From the terminal**
  ```
  1. mkdir imagepy
  2. cd imagepy 
  3. touch img2txt.py
  4. open folder within VScode 
```
## Step 2. write a couple lines of code
```
import cv2                                                                                         
import pytesseract                                                                                 

img = cv2.imread('kitty.png')  # <<---- insert image path here                              

text = pytesseract.image_to_string(img)                                                            

print(text)
```
## Step 3.  Find your pic and hit Play
This is a pic of my qtile configs
![kitty.png](https://imgur.com/VlyviPo.png)


![](https://imgur.com/f0ywglU.png)
This is the output
![](https://imgur.com/iLwgoj1.png)
So it did a pretty decent job, it had some trouble with all of my commits. After its complete just copy and paste what you want to do with the text.


