# **MetaDoggo**

Category: Forensics

Author: Tharun K

Answer / Flag: `MAZE{d0gg0s_4r3_cut3}`

## Problem Statement

I think this dog has a flag, can you retrieve it for me?

## Relevant files / links

`doggo.jpg`

## Hint

The photographer has left some comments and his copyright info, can you find it out?

## Solution

From the metadata of the photo (https://exif.tools/), you'll get the following


- User Comment: `IEZV{d0bo0y_4n3_guk3}`
- Copyright: `V2VhckFWaWc=` this is Base64 encoded version of `WearAVig`,

Which suggests that it's a Vigenère encoding, with `WearAVig` as key and `IEZV{d0bo0y_4n3_guk3}` as payload


https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('WearAVig')&input=SUVaVntkMGJvMHlfNG4zX2d1azN9
