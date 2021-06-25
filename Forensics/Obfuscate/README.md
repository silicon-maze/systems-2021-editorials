# **Obfuscate**

Category: Forensics

Author: Balajinaidu V

Answer / Flag: `MAZE{0bfu5c4710n_0f_fl4g}`

## Problem Statement

After n00b_h4ck0r tried to access Tony's system, Incident response team checked the logs and found this Suspicious command that was executed. Malware authors try to obfuscate their payloads. Can you analyze this command without running it!

`$s=New-Object IO.MemoryStream(,[Convert]::FromBase64String("H4sIAEP1yGAA/y3KMQuCIRCH8a/y52gNDIyGeIeGxrYgaJFLPRXkNfIaIvruOrT9Hnhur6Jxm1tX0DVHSOWE0lFW6Mz2kHf3rDHgyZ/aONARmz+xgC6n+/lr5rX39rAzqzPipNr0owEjEnFMWgAAAA=="));IEX (New-Object IO.StreamReader(New-Object IO.Compression.GzipStream($s,[IO.Compression.CompressionMode]::Decompress))).ReadToEnd();`

## Hint

Can you read something which is not obfuscated?

## Solution

As the problem statement says this is a obfuscated shell command. Two key things to note in the command
- [Convert]::FromBase64String
- Compression.GzipStream
`H4sIAEP1yGAA/y3KMQuCIRCH8a/y52gNDIyGeIeGxrYgaJFLPRXkNfIaIvruOrT9Hnhur6Jxm1tX0DVHSOWE0lFW6Mz2kHf3rDHgyZ/aONARmz+xgC6n+/lr5rX39rAzqzPipNr0owEjEnFMWgAAAA==` this is the obfuscated payload. Using a tool similar to [Cyberchef](https://gchq.github.io/CyberChef/), we can first decode the payload from base64 encoding and then decompress the gzip compression, we get the flag.
![solution](https://i.imgur.com/V2anBn9.png)
