---
layout: post
title: "Create an Animated GIF from a Quicktime Screen Recording"
date: 2018-11-02 16:00:00 -0500
categories: [ "How To" ]
---

Projects need documentation. Lately, I’ve been jazzing up my docs with animated gifs made from screen recordings (MOV files) out of Quicktime. Its surprisingly easy!

There are some tools and Terminal commands, but I like the fact that I don't need to upload something to a website and then download the results. I'm technical, but not super technical, so this was just the right level for me. 

I used instructions from [a GitHub Gist](https://gist.github.com/dergachev/4627207) which details installation and running the conversion commands. Here it is again for posterity, with my own additions from my experience:

## Installation

The conversion process requires **ffmpeg** to process the video file and **gifsicle** to process the animated gif. The following command-line directives use [HomeBrew](https://brew.sh) to install and manage the packages:

```bash
$ brew install ffmpeg 
# dependency for gifsicle, only required for mountain-lion and above
$ brew cask install x-quartz 
# runs the XQuartz installer
$ mopen /usr/local/Cellar/x-quartz/2.7.4/XQuartz.pkg 
$ brew install gifsicle
```

## Quicktime

There are other tools out there for creating screen recordings, but any Mac user should use the included Quicktime software to get it done. Its super easy and nothing extra needs to be installed. 

1. Open <kbd><kbd><samp>Applications</samp></kbd> > <kbd><samp>Quicktime</samp></kbd></kbd>
2. Choose <kbd><kbd><samp>File</samp></kbd> > <kbd><samp>New Screen Recording</samp></kbd></kbd>
3. Follow the instructions, or click and drag on the section of the screen you wish to record
4. An optional effect is to have Quicktime highlight the mouse clicks. Give it a try, you might like it.
5. Save the movie to the directory of your choice

## Conversion

In the Terminal (or any command line interface), navigate to the directory in which your videos are stored. The command I run is this: 

```bash
$ ffmpeg -i input.mov -s 600x480 -pix_fmt rgb24 -r 10 -f gif - | gifsicle --optimize=3 --delay=8 > output.gif
```

Where `input.mov` is replaced with the name of your video file and `output.gif` is replaced with the name you wish to give the new animated gif. 

A few notes on portions of that command: 

+ `600x480`: This is the desired output size. The aspect ratio of your original video should be maintained if you are resizing it. Otherwise this conversation will distort the original video. I use [a tool from Andrew Hedges](https://andrew.hedges.name/experiments/aspect_ratio/) to figure out the aspect ratio and maintain it for resize. 
+ `rgb24`: Color depth of the output. I tried rgb8 thinking that the file size would be significantly smaller, but for a screen recording, the color depth was poor and the compression patterns made it look awful.
+ `-r 10` refers to the frame rate. 10 seems low but it looks pretty good for screen recordings. 
+ `--delay=8` creates an 80ms delay between frames. The original command had this set to `3`, but things looked unnaturally sped up. I found that `8` makes the speed of the gif seem more natural. Depending on your movie, you might want to adjust the delay until the GIFs look to be a good speed.

## Profit

And now my online tutorials and client training documentation look great. It can really help to see an animated gif of someone moving through a particular feature — it explains it better to see it in real time rather than just explained in static text.
