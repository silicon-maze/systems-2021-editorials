# **Two Fake stones**

Category: Web

Author: Srujan Bharadwaj

Answer / Flag: `MAZE{FUN_SCRAPING_AND_ENCRYPTION}`

## Problem Statement

You enter here: https://srujangit123.github.io/Silicon-Maze-Web-task/index.html. There are infinite infinity stones around you. There are two fake stones among them. One stone is helping in hiding something in another stone. Can you find what's hidden?


## Relevant files / links

[index.html](./index.html), [image.jpg](./image.jpg) and [styles.css](./styles.css)
The page is hosted [here](https://srujangit123.github.io/Silicon-Maze-Web-task/index.html)

## Solution

The first thing to note is the format of the youtube video links. Every youtube video contains 11 unique characters after ``https://youtube.com/watch?v=``. So, get all the links present on the page. Then for each of those links check if it is valid or not. You get two links which are invalid. Now use these two video IDs(characters after v= in the link) to get the flag. One ID is a secret key and another is an encrypted text. Also the [background image](./image.jpg) hints that this is an AES Encryption. The flag can be obtained by decrypting the text with the secret key.

These are the two invalid links:

- https://youtube.com/watch?v=<strong>a6kufTRVSM6UZu7Qreeiz0K9LiqhOwuwFs4jpfp8EZ6fED39bS4QD1tld5EswgUl</strong> - Hash(in base64 format)
- https://youtube.com/watch?v=<strong>kRzgVih9pcRO8SNb</strong> - Secret
- [This](https://www.devglan.com/online-tools/aes-encryption-decryption) online tool can be used to decrypt the text.
