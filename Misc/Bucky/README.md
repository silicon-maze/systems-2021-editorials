# **Bucky's Dilemma**

Category: RE

Author: Rakshita Varadarajan

Answer / Flag: Not in the format of MAZE{<>}
`951a1d95f6ffdceba387dbe5a0b5630d95f48b5c30e8b4c833fff6f252cd653a1921`

## Problem Statement

Captain America sent a secret file along with a voice note saying: "Let's hash this plan out. It is important to make the right Call with 'Whatever It Takes' " to Bucky Barnes.

Can you help Bucky find the hidden flag to help him defeat Hydra?

## Relevant files / links

[Captainshelp.py](https://drive.google.com/file/d/1tgqWq7_R76MnUOiNqOWFOi7scD9_ekC-/view?usp=sharing) 


## Solution

On running the file, it basically gives ACCESS DENIED no matter what. This is because the wrong function is being called in the file. On calling the correct function (unlock_ans), you can see its calculating sha256 of whatever string is passed. The voice note mentions Calling with "Whatever It Takes", and thus on passing this to during function call you get the required hash value to unlock the flag.
