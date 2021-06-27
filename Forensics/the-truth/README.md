# **The Truth**

Category: Forensics

Author: Sudarshan

Answer / Flag: MAZE{therealkillerisBaronZemo}

## Problem Statement

T'Challa, the benevolent and helpful king of Wakanda, received an anonymous message with a note saying "Everything about your father's death is in here" along with a file titled "the-truth". However, there seems to be some issue with the file. Can you help this helpful king with his problem? (Submit in the form MAZE{answer})

## Relevant files / links

Link to file: [Drive Link](https://drive.google.com/file/d/1CPfbebBA5tRrs6xV062ekFpeSf1jqOE3/view?usp=sharing)

## Hint

The fortified walls may hold the hidden truth away from the helpful king.

## Solution

The file is basically a ZIP file (you can find this by running `binwalk the-truth` on the terminal). Now you can extract the files in the ZIP by running `binwalk the-truth -e`. This will extract one file (*beautiful-fort.jpg*), but give you an error as well. To find the issue, you can just open this file in a hex editor or run `hexdump -C the-truth | more`, where, instead of the magic bytes for a zip, you will find hEllo as the first 5 characters (`hex: 68 45 6c 6c 6f`). Replace this with the magic bytes for a ZIP  file, and then extract the remaining file.

Open the *beautiful-fort* image. You won't find anything suspicious if you just open it, but on running the strings command, you will find some text in the end - **Find the key to this Beautiful Fort that contains the truth: aaakagxdfxccczmAepuaOebs**. The "beautiful fort" hints that you will have to use the Beaufort cipher. To find the key, the image *a-secret* may be useful.

Open the image *a-secret* which has some cryptic language text in it. This is basically the Wakandan script (going along with the theme and the question). You can take the help of the *helpful* king or just Google the Wakandan script to decode this. You end up with **THE BEGINNING IS THE KEY TO THE TRUTH**. At first, it may seem like some metaphorical statement, however, the key that you need for decrypting this cipher is quite literally "THE BEGINNING" \[without the space\]. You can use any online tool [like this](https://www.dcode.fr/beaufort-cipher) and decipher it to find the *truth*.




