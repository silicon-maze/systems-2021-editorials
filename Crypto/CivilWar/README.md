# \<**The Civil War**\>

Category: Crypto

Author: Rakshita Varadarajan

Answer / Flag: `MAZE{1RoNm@nIs0&c@ptain1s1}`

## Problem Statement

Hawkeye was sending battle strategies as encoded messages to Wanda, but forgot to include the decoding strategy. He quickly sends across the below (encoded) file along with a note that reads: "Captain America is Greater Than Iron Man. He is the ONE!" 

## Relevant files / links

[important.txt](./important.txt) (drive link for same file: https://drive.google.com/file/d/1pPi_EO8ud0qRMGACb9-Im4BdNE4_tzMF/view?usp=sharing)

## Solution

The file has symbols of Greater Than and Less Than signs. The message sent reads Captain America is Greater Than, and he is ONE. So replace all Greater Than's by 1, and its implied that the Less Than's will be 0. Ascii decode the binary string and it gives a base64 text with "Prepping Base" message. On decoding base64, you get the flag.
