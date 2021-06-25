# **FindMyPhone**

Category: OSINT

Author: Tharun K

Answer / Flag: `MAZE{43.78364182,-79.24232483}`

## Problem Statement

I lost my phone near a Wi-Fi hotspot while I was using a famous Wi-Fi logging app. I have the details of the last SSID my phone captured. Can you get me the location of the Wi-Fi hotspot, i.e. latitude and longitude (8 decimal places)

- Flag Format : `MAZE{Latitude with 8 decimal places, Longitude with 8 decimal places}`, no spaces in the flag
- SSID : `ESCN`
- BSSID Address : `68:8F:2E:1C:DD:88`

## Hint

Find a famous BSSID address lookup / Wi-Fi hotspot logging site

## Solution
Use wigle.net, it has an advanced search option to look up the MAC Addresses

https://wigle.net/search?netid=68%3A8F%3A2E%3A1C%3ADD%3A88