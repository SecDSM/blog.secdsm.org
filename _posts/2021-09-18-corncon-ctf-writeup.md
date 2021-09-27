---
title:  "CornCon 7 Crypto Challenge CTF Writeups"
categories: [ctf, ctf writeup]
tags: [CornCon, CTF]
toc_h_min: 1
toc_h_max: 2
---

The annual CornCon conference was held Sept 10-11, 2021 and the Crypto Challenge CTF featured challenges that could all 
be done in a remote fashion, allowing for a great opportunity for SecDSM members to participate in the conference 
remotely.

There were a total of 10 challenges presented, which followed the CornCon 7 theme of "Cyber Things", a pun/spin off of 
the popular Netflix series, Stranger Things.

We were able to complete the board and secured a first place finish.

<!--more-->
# Challenges
## Ghost of CornCon past
### Clue
```text
Themes are important. So is remembering where you came from.
What was the slogan / subtitle for Children of CornCon IV?
```
### Solution
Knowing that "Children of CornCon" is the title for CornCon's `kids` conference, this was more of an issue of figuring 
out which year was CornCon 4 and finding some references to the kids track.  CornCon being well known for their movie 
based themes each year, I assumed the subtitle would be in some marketing material from the year. 

So, being that 2021 was CornCon 7, CornCon 4 would have been 2018, so I headed over the 
[2018 Kids Schedule](https://corncon.net/2018.corncon.kids.agenda.html) on the official CornCon website, and came up 
empty handed.   

Finally, I headed over to twitter and looking for tweets from the 2018 timeframe, I came across 
[a tweet from @MrJeffMan](https://twitter.com/MrJeffMan/status/1021762902334816259?s=20) which contained a subtitle 
`Harry Hack and the Coblet of Cyber` which was the solution

![Tweet Image]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/tweet1.png)

As a sitenote - I actually found a challenge coin from this year for sale on 
[ebay](https://www.ebay.com/itm/Cyber-Security-Coin-Harry-Hacker-and-The-Goblet-of-Cyber-Security-Challenge-Coin-/284143933163)

![Ebay Image]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/ebay.png)



## Upsidedown
### Clue
```
H4sIANgcOmEA_w3Ux66CQBTH4ScikVZcDkVEei-bCa04CNIGhKe_d3tW_5x8-T2ZVQNWWdqDAuBBB17KKSEA4ObZHmMYgm9bWPawhC93nliBPaIt9FeNVuvuKL6M5Eu8WUW6vx0KMNWVw3r6YpLAIrZc394ed8t9T8o-ZWWbwpFUTH_runeZ3HLACou3zlLovT9wI4oheZ46VrUTfOwbxPLl78asCtKiVee8XqyOidJzFhFSfVBXU6WJpAenqW2jXfYiGpG_-GIO8v3UC86KOTQJSXk0HyCe8af3uusB7VL_tikaECQ14v0RIuLwVVeJAtdCpPWY2-kn7crwYfbPiazfXKin-ooGU5a4xJnXUsmIavDSxNsRpRSESymnaAwBKmAs5EudX5Eed3nGu9NIRrzceVK3uYCA0laFi_27-Zz-Tl4rdIvTbVb1kCH0ZcOza7esIjWGLay_erZOe6sSLr4TVwyNr1OVzlbfkL4vtcCLwf6WG3sh8McY6Z-w__-5TggLvMhdR0FFbJRoR49BZtaw-95YN6G00kVAqdwrYKRx_ZIZZiBCbWqa_kVzbCg4zpv9P2TlwS-_3-VFL7W694YuoSs_bGvEkTn1C60r8aDBjsr6hgvEG5Fq7gzPh5-XWRKJ-Vl3AQZ9fbz7Jnr2JnqzVPGdWPE-eQk-Mwna5IMIvxd49KQ1QYwN_vdwRyWNv9s1DBkN-GWSXYq0OE7xg5-G5w9-RejXCiDqezKckvyO1RMSc9U1Lt1HuVpwrvTM1bvhBTm_B1SGNxQL3k9v7O_oCOL0rSQrmULGyYkGh8nyr7Dn4_W3oY1wCr_T_DvsHKWxzmdASGrgiCPe1F1oKSpQonsvpd9x3R9Gr4wynAwEV4ieQ5iItiXa_GaGxv_mnH3Rxy17Ycb6NKpIwf3Fm-VboEf_a3cVyPlukQsyBloKG8Sk7fAeszF9Up84G3jz8IKVhspkOcp3uCtEYJ04mnF0r44O9EvD4jjQaDmuRqyMouPRyr88REYtvl_WaJrDjMCwqLv9kFoh1IolGyJwWRQ5lub9iSYy0MBP-hz5IB5wu2wzpGmSeLAN12Y0O6CAIrlZgYM3D_rSg0VJpjG84dWZmXae-Cpge5dEbQdtcyREotG1p8E5sbWSdW6FKWHt94o6eo6cR0fLwmVADzoqR22zZcN2fzNtl22LcJE8ynX2HvboLGfxPkqYU8LQn-X9PSdabgqGnZs1zZvazTXEVPgvAm9UH4D3UOi2eoRRYZI_FWtdiI458gUDAnwr2XxgUG-9PJYxzSa60dwiKqgWTzWss-d5nRJIZS-xq7QBYZYG9vg6otnOsPgPLbfKcN_xQzpbWS8t58k876qw6oIuybXvnln4AM4h3seC1-z_wAHwBylgTbwvBQAA
```
### Solution
A quick "eye" of this blob, base64 was a good guess.  Initially, the use of cyberchef to base64 decode the string 
indicated a non-ascii result.   

![upsidedown_1]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/upsidedown_1.png)

However, CyberChef also features a "Detect File Type", which indicated this was gzip compressed data.  But when 
attempting to apply the "gunzip" operation an error was produced.  Turns out this was due to the way the base64 was 
generated.  If we turn this to "urlsafe" as seen in the below image, the decoding worked well. 

![upsidedown_2]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/upsidedown_2.png)

Once we had a successful decode of the second layer, we could again use the "Detect File Type", it was indeed gzip 
compressed data.  With the clear pattern, we can just continue adding the "base64 decode (url safe)" and "gunzip" combo 
until we get an answer.  After the conference, I re-worked this using the `Jump` function to avoid dropping in 46 
different "operations" into cyberchef.  

![upsidedown_2]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/upsidedown_3.png)

Here is the receipe in JSON format that can be loaded directly into cyberchef

```json
[
  { "op": "Label",
    "args": ["start"] },
  { "op": "From Base64",
    "args": ["A-Za-z0-9-_", true] },
  { "op": "Gunzip",
    "args": [] },
  { "op": "Jump",
    "args": ["start", 21] }
]
```



## Dubbel
### Clue
```
Solve the picture
```

![corncon_1.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_1.png)

### Solution
Dubbel presented itself as a [substitution cipher](https://en.wikipedia.org/wiki/Substitution_cipher), and a great one 
to get started in recognizing pattens and applying context to discover the answer. 

The first observation made was that the image displays a total of seven positions and only four unique "shapes" where 
the shapes in position 1, 2 and 4 (from the left, going to the right) are repeated at the end of the image in positions
5, 6, and 7.

Understanding the name of the conference as context, it can be observed that `CornCon` is also seven positions, with 
only for unique "shapes" (english letters in this case), where the letters in positions 1, 2, and 4 are repeated in 
positions 5, 6, and 7. 

Attempting `CornCon` as the flag, was accepted as the correct answer.


## 10th level Ranger
### Clue
```
Solve the picture
```

![corncon_3.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_3.png)

### Solution
10th level Ranger was a surprising difficult challenge to solve.  Having a relatively low point value, after spending a 
about 30 minutes attempting different cipher methods (ROT13, other substitution cipher, keyed ciphers) it was decided 
to move along.   

Finally, during the SecDSM Friday Night hangout, the group reviewed this challenge.  The solution was rather simple and 
displayed the entire time the image was being viewed. 

Looking at every other letter relieved the solution of `MIND FLAYER` - a clear reference to the Stranger Things theme.

![corncon_3.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_3_solve.png)

A great challenge that really showed how frustrating a rather simple challenge can be when focusing on complex 
solutions without attempting more simple "visual" solutions.

## Squiggly-wiggly
### Clue
```
Solve the picture
```

![corncon_2.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_2.png)

### Solution
Squiggly-wiggly presents itself as an image, with 5 columns of variable length, reminding me of the "Matrix" screen 
effect of text letters falling from the top of the screen.  When looking at the first shape of each column they are 
constant, with no variation.  Looking at the last shape of each column also reveals each ending with the same shape, 
distinct from the "start" shape.  This reminded me a bit of 
["magic bytes"](https://en.wikipedia.org/wiki/File_format#Magic_number) and "footer/trailer" bytes. 

Working under the assumption these were "start" and "end" shapes, I began to identify the unique shapes in the image. 
Creating a grid on the image itself helped in identifying the unique shapes where the shapes were "connected". 

![corncon_2.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_2_grid.png)

After creating the grid, a manual key was created and english letters were assigned to each unique shape.
```text
A   D   D   D   C
B   A   F   I   K
C   E   B   F   C
    B       B   E
    D       J   L
    A       C   M
    B           I
                N
                B
                J
```
 
After each shape was assigned a letter, they were arranged by column into a single row, and throw into a great online 
tool - [quipquip](https://www.quipqiup.com/) and solved in about a second 
```
ABC DAEBDAB DFB DIFBJC CKCELMINBJ
```

![corncon_2.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_2_solve.png)

## Don't Cross the Streams
```
Solve the picture
```
### Provided Files
![corncon_9.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_9.png)

## Extra Life

### Challenge
```
Solve me
```
For Extra Life - there were two provided files
First was in image

![Grid.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/grid.png)

Followed by a [text file]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/solveme.txt) 
containing a single line

```
ULULUL LDDLLDDLL LDDLLLDDL RURRUR,  DLDL LUULUL LLLL   LUUUULU'LUUL   DDLLLLDD LLDLDD LRDD LUUULUU UURURURU RRRUURR   DRRDDDD UULLL,  LLDDLL DRDR LLLULLU RDRR   DDRR DLLDDL RRRRRDD LLLDDDL   ULLUUUU LUDDU   UURRR LD RUURURRR RDDRRRR URDRRRDDUU   DDRDDRD UUULR   LLLLULU UUUR DRDRRDDR RDDRDDD UURUL URRURRR?  UULU LUULLUUU URRRURRU   ULLUUULU DDLL RRRDDDDD DLLLDDDDLL   UUUULLU UUUURRRU   RDR DUUDL UURRRR DDRDDRD DRDDLD LRRRDDDLLDD   UULUUUL URUU   UUUL RDDR RDR DRRR   UULU DURR RUR   DLR DRDRDDD LDDDLD DLDLLLDUUU   LUDUD LLULLUL URLRRLL   RUUUL LDLLDDLDL.  LLULD ULU   LLDDDL LDDDDLLL RRRRUU   LDDDD RR RDRDRRR   UUR LDLLDLDDL RDRRDRR URRURRR LULUUUU LLLLD RURRRRUU RUURUUUR URRRRRUU RUUU UDUDL,  DDRRLRLDLD URRUDD URRUR   LLULLU URRRRRUU DRDRDDDR LULU ULULUUU LLDDDLLD LLUUL UUUULLU RDDUUR URUURUUR.  LDLD LURUU RRDDDDR   ULULUUU ULLUULU   LUUU RDDR LUUUUUL RUUU   L UULU LDDLDLLLD RRDRRDR DLDR'LLLDDLDD   RDR LLLUU   DRRDDDRLLLD DRUR DRUR RUUURU   ULULLLL UUUR   I   DRRR LULLUUUU UUULULU UURURRUU RRURUR   DDDDRDR RDRR'DDULU   DDL DDLDLDLLL RDDDDL DLDDRD DLLDLD   RD LUU,  UUUL LUULULUU UURRRRRU LURUU   LUUU DDLDLLLLD DLDDLDDLLL   LLL UURDUDRD DDLRDD'ULUU   RDRDR DDLL RDRRDDDD URURRRUR.  UURRR LD LUU   RRD LUUUR L RURU RRRR DRDRRRR   RDDDDRD ULLUL   RDDRDRDR LU DLDRDLRDRL LLLULLU RUR ULUULUU.  UUUUULL RRUURUUU   LLLUUUL RRD LL RRURU,  ULUUULLU RRRURUUR'UULLLU DDLLDD   UURRR DRDR RDR URRRLULLU RDDRDRRD   LDLDD DUL.  UL DRDDRDRD   RRUUR LD RRRURUUR   LDLDLDLLD LLLUUU RRDDDRD   LDULULDL DLDDLL DLLL LRUU   DDDRRDD UDUDL   ULURU DDDDR RDRR DUL   DRR UUURURRU LLLD   RUURR UULLLUUU RRRRUURU   LDUDUUD DRRR LU DRRRDRR LRU   DRDRD DLLDDD RR LRD DLDDLLDL   DDRDD LLLLUU   UUUULLU URRUUUUR   UDRR RDDDD DRRRRDR   RUU LLDD LLDLLDLD RRRDUUDRDU   DRR DRLDDD RDDRRDD   RRUUR UL LLLDDLDLDD   UUUULLL RDDRDDD DDRDDRDR URDDURRR DDLLDLLD   DRDDD DUUDULD.
```

## Lab Homework
```
One of the sensors on the Hawkins National Laboratory’s public facing dashboard is displaying some weird unreadable messages. Can you take a look?

Dashboard: 54.80.132.176
```


## Typo Squatting
### Points: 500
### Challenge
```
What is in my traffic?
```
### Provided Files
[pcap]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_5.pcapng)
### Solution
## Don't Blink
### Points: 600
### Challenge
```
Solve the animated pic
```
### Provided Files
[corncon_7.gif]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_7.gif)
### Solution

## What's your Vector, Victor?
### Points: 800
### Challenge
```
Our sensor network detected an anomalous power surge at 1500. We were able to calculate the source to a location just behind Hawkins Library.

Please use the data to help us calculate where the power spike occurred at 0330.
```
### Provided Files
[Hawkins_Map.jpg]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/Hawkings_Map.jpg)
[hawkins_stats.csv]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/hawkins_stats.csv)
### Solution

## Junior Panda Swim Team
### Points: 900
### Challenge
```
Solve the text

```
### Provided Files
[corncon_4.txt]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_4.txt)
### Solution

## Influencer
### Points: 1000
### Challenge
```
I was driving through town making a video for my YouTube channel and I heard something wierd come across the radio...

Can you help me figure out what it was? Until then, I'm just going to post the video without any sound.
```
### Provided Files
[corncon_8.mp4]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_8.mp4)
### Soultion

## Town Square
### Points: 1200
### Challenge
```
We recovered this file from the remains of the lab, but it appears incomplete.

Maybe you can fix it and help us solve the mystery.
```
### Provided Files
[invasion.js]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/invasion.js)

