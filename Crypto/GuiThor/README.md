# **He hasn't met GuiThor?!**

Category: Crypto

Author: Sudesh Gowda J

Answer / Flag: `MAZE{LOKI ON MOON}`

## Problem Statement

Nick is in search of a villain. He has sent this weird image in which there is location of the villain.
But I'm pretty sure Nick told me that there are 11 numbers in this image and that 11th number is the key.
Find the details and report back.

Flag format: MAZE{<flag here>}

Convert all letters(if any) in flag to capital letters

## Relevant files / links

https://drive.google.com/file/d/1SWMkrkfig3ZrTuCY0Vnp44aA-_wvvyF8/view?usp=sharing

## Hint

"Note" down the numbers

## Solution

The image given is of guitar tabs. This can be figured out by image search.
These numbers are positions on guitar which give different notes. Decode the notes from the tabs [reference](https://www.jazz-guitar-licks.com/blog/cheat-sheets/notes-on-guitar-fretboard-diagrams.html).
Decoding the 10 notes from tabs will give you "DGCA GF EGGF".
There is a mention of an 11th hidden number. Use steganography on the image to get the number 8.
Online tools similar to [this](https://stylesuxx.github.io/steganography/) can be used to decode the message from image.
8 is said to be the key. Now using ceaser cipher with key as 8, we get the final message as "LOKI ON MOON"
