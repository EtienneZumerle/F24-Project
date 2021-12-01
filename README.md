# F24 Macro keypad 
## Table of contents
1. [Introduction](#introduction)
2. [why did I built this ?](#why)
3. [how does it works ?](#how)
4. [3D Printing](#3D)
    + [Case](#case)
    + [keycaps](#keycaps)
5. [Electronics](#electronics)
    + [Design](#design)
    + [Routing](#routing)
    + [Soldering](#soldering)
6. [Software](#software)
    + [Arduino Code](#code)
    + [Auto Hotkey script](#ahk)
7. [Things that can be improved](#improve)


<div id="introduction">

## Introduction 
This is the F24 macro keypad, with 8 mechanical keys to bind macros and 5 rotary encoders to control app sound volume.

![F24](figures/F24.jpg)


<div id="why">

## Why did I built this ? 
I had the idea to build this during lockdown, at the time I played different video games, sometimes while listening to music, chatting with friends on discord or watching Youtube videos.</br>
I also attended online classes on Zoom, Discord or Microsoft Teams.</br>
That meant I had to open the windows sound mixer every time to manage sound volume and it got a bit too annoying. 

<div id="how">

## how does it works ? 

+ It uses an Arduino "Pro Micro" (ATmega32U4) to send keystrokes through USB</br> 
It turns out that keys `F13` to `F24` are still suported by Windows (they were used on some very old keyboards), it's a easy and simple way to send keystrokes while never interfering with other applications. </br></br>

+ The recieved keystrokes are assigned to actions like Spotify volume up, next track, launch a specific app... but it could be anything thanks to the power of [Autohotkey](https://www.autohotkey.com/) </br> 

<div id="3D">

## 3D printing

<div id="case">

### Case

![assembly](figures/assembly.png)


+ **the bottom piece**</br></br>
    - I recommend using super glue to place the M3 nuts. **Don't use a soldering iron** because it will uncenter the nut and you won't be able to bolt the bottom to the top.</br>
    - Use 12mm long M3 Bolts for every hole.</br>
    - The 2 flat steel bars are not mandatory but it adds weight and makes the keypad more stable when you use the encoders </br>

![bottom](figures/case-bottom.png)

[\<mark>](https://github.com/markdown-it/markdown-it-mark)

==Marked text==

+ **the top piece**</br></br>
    - Use the same M3 nuts 

![top](figures/case-top.png)

<div id="keycaps">

### Keycaps

<div id="electronics">

## Electronics

<div id="design">

### Design

<div id="routing">

### Routing

<div id="soldering">

### Soldering

<div id="software">

## Software

<div id="code">

### Arduino Code

[*Keys are assigned like this*](#code)
- Encoders

| encoder | output (clockwise)   | output (clockwise)  |    output (pushed)   |
|--------:| :-------------------:| :------------------:|:--------------------:|
| 1       | `KEY_F24`            | `KEY_F23`           | `KEY_F20`            |
| 2       | `KEY_F24 && KEY_F23` | `KEY_F22`           | `KEY_F24 && KEY_F20` |
| 3       | `KEY_F24 && KEY_F22` | `KEY_F23 && KEY_F22`| `KEY_F23 && KEY_F20` |
| 4       | `KEY_F21`            | `KEY_F24 && KEY_F21`| `KEY_F22 && KEY_F20` |
| 5       | `KEY_F23 && KEY_F21` | `KEY_F22 && KEY_F21`| `KEY_F21 && KEY_F20` |



- Keys

| row/column | col 1                | col 2               |col 3                |col 4                | 
| ----------:| :-------------------:| :------------------:|:-------------------:|:-------------------:|
| row 1      | `KEY_F19`            | `KEY_F24 && KEY_F19`| `KEY_F23 && KEY_F19`| `KEY_F22 && KEY_F19`|
| row 2      | `KEY_F21 && KEY_F19` | `KEY_F20 && KEY_F19`| `KEY_F18`           | `KEY_F24 && KEY_F18`|


<div id="ahk">

### Auto Hotkey Script

<div id="improve">

## Things that can be inproved
