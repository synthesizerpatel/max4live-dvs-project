# Project max4live-dvs-project

## Description: 
I want to recreate my old Reaktor project max4live device that can drive a sample playback buffer
using the analog-to-digital style "digital vinyl signal". I have provided several wav files in the
timecode-example directory of the repo.

I have a few examples of it in action, using a digital vinyl signal to play samples that get 
injected into the scratching stream. Please forgive the bravado of youth, 16 years ago I thought
I was a cool guy for doing stuff that people like mspinky pioneered. Forgive me. I was a dumb kid.

* https://www.youtube.com/watch?v=5ZI-0zagrvU
* https://www.youtube.com/watch?v=yZ2jTG7OLss

For a detailed explanation about how digital vinyl .. kind of works, this is a great write up
https://mixxx.org/news/2021-11-21-dvs-internals-pt1/ but I've been told there's a better way 
to do it with FFTs. I'm too lazy to bother to do it in a VST because thats a lot of work and I'm 
fairly certain it should be possible to cobble together something without even needing max4live 
externals.

Getting the smoothed value of frequency detected lets you know how fast the record is spinning, 
supposedly you can do a carttopol to get the magnitude and phase of the left and right signals but
I don't know beyond just using multiple windowed FFTs? If you know FFTs, you could be the person
for the job.

## The goal of the project is:

* Real-time process an incoming stereo signal using a set of windows FFTs to detect phase of L/R signal (direction)
  a fairly accurate frequency (speed of rotation) and then apply that value to a stream of samples to scratch them.

* It will be free for any max4live user. 

* This should be a stock piece of gear for people who use DVS systems, just for doing stuff like
  interfacing with DMX light stuff or OpenSoundControl at the very least.

