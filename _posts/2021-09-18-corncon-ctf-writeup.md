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

As a sidenote - I actually found a challenge coin from this year for sale on 
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

Understanding the name of the conference as context, it can be observed that `Corncon` is also seven positions, with 
only for unique "shapes" (English letters in this case), where the letters in positions 2 and 4 are repeated in 
positions 6, and 7. 

Attempting `Corncon` as the flag, was accepted as the correct answer.


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

Working under the assumption these were "start" and "end" shapes, focus was placed on identifing the unique shapes in 
the image.  Creating a grid on the image itself helped in identifying the unique shapes where the shapes were 
"connected". 

![corncon_2.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_2_grid.png)

After creating the grid, a manual key was created and English letters were assigned to each unique shape.
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

### Solution
TODO

## Extra Life
### Clue
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

### Solution
Being familiar with how old cheat codes, such as the [Konami Code](https://en.wikipedia.org/wiki/Konami_Code), were 
shared along with a large dot in the middle of the provided grid provided a quick understanding of how to solve the 
challenge.

Each letter in a space seperated "word" represents a single "instruction" (quick table below), once the final instruction is 
hit, this represents a single letter of the word.  Each word is double space seperated.

|letter|instruction|
|------|-----------|
|U|Up|
|L|Left|
|D|Down|
|R|Right|

As an example, the below gif walks through the first few words of this challenge. 

![extra_life_prcess.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/extra_life_process.gif)

There were two ways to solve this, manually or writing a small script/program to run through the "commands". 

During the actual CTF, the option to complete this challenge manually was selected, and being hackers, shortcuts were 
taken, but eventually the slow road was taken for a subset of the commands.  

To facilitate completing the challenge manually, the grid was recreated in LibreOffice Calc and using the arrow keys on 
the keyboard to find the correct letter.  A quick pattern appeared and a DuckDuckGo search allowed us to fall down a 
rabbit hole. 

The shortcut attempted was to google the phrase that was appearing after the first few words were completed.  It turned 
out to be a quote from [Stranger Things - Season 3 episode 02](https://8flix.com/assets/transcripts/s/tt4574334/Stranger-Things-episode-script-transcript-season-3-02-Chapter-Two-The-Mall-Rats.pdf)
```
Look, all I'm saying is, what harm is there in asking? The harm in asking is that Tom will say no. We ask for forgiveness, not permission. And if this story's as good as I think it's gonna be, then Tom won't care. In fact, he'll thank us. Or the old lady is nuts and the story blows up in our face and Tom fires us.
```

In lining up the punctuation, everything seemed correct, but attempted submissions of this quote did not work....hmmm

The quote and the entire original clue were lined up, matching on all the punctuation to see if there were any parts 
that did not make sense.  

```
ULULUL LDDLLDDLL LDDLLLDDL RURRUR,  DLDL LUULUL LLLL   LUUUULU'LUUL   DDLLLLDD LLDLDD LRDD LUUULUU UURURURU RRRUURR   DRRDDDD UULLL,  LLDDLL DRDR LLLULLU RDRR   DDRR DLLDDL RRRRRDD LLLDDDL   ULLUUUU LUDDU   UURRR LD RUURURRR RDDRRRR URDRRRDDUU   DDRDDRD UUULR   LLLLULU UUUR DRDRRDDR RDDRDDD UURUL URRURRR?  UULU LUULLUUU URRRURRU   ULLUUULU DDLL RRRDDDDD DLLLDDDDLL   UUUULLU UUUURRRU   RDR DUUDL UURRRR DDRDDRD DRDDLD LRRRDDDLLDD   UULUUUL URUU   UUUL RDDR RDR DRRR   UULU DURR RUR   DLR DRDRDDD LDDDLD DLDLLLDUUU   LUDUD LLULLUL URLRRLL   RUUUL LDLLDDLDL.  LLULD ULU   LLDDDL LDDDDLLL RRRRUU   LDDDD RR RDRDRRR   UUR LDLLDLDDL RDRRDRR URRURRR LULUUUU LLLLD RURRRRUU RUURUUUR URRRRRUU RUUU UDUDL,  DDRRLRLDLD URRUDD URRUR   LLULLU URRRRRUU DRDRDDDR LULU ULULUUU LLDDDLLD LLUUL UUUULLU RDDUUR URUURUUR.  LDLD LURUU RRDDDDR   ULULUUU ULLUULU   LUUU RDDR LUUUUUL RUUU   L UULU LDDLDLLLD RRDRRDR DLDR'LLLDDLDD   RDR LLLUU   DRRDDDRLLLD DRUR DRUR RUUURU   ULULLLL UUUR   I   DRRR LULLUUUU UUULULU UURURRUU RRURUR   DDDDRDR RDRR'DDULU   DDL DDLDLDLLL RDDDDL DLDDRD DLLDLD   RD LUU,  UUUL LUULULUU UURRRRRU LURUU   LUUU DDLDLLLLD DLDDLDDLLL   LLL UURDUDRD DDLRDD'ULUU   RDRDR DDLL RDRRDDDD URURRRUR.  UURRR LD LUU   RRD LUUUR L RURU RRRR DRDRRRR   RDDDDRD ULLUL   RDDRDRDR LU DLDRDLRDRL LLLULLU RUR ULUULUU.  UUUUULL RRUURUUU   LLLUUUL RRD LL RRURU,  ULUUULLU RRRURUUR'UULLLU DDLLDD   UURRR DRDR RDR URRRLULLU RDDRDRRD   LDLDD DUL.  UL DRDDRDRD   RRUUR LD RRRURUUR   LDLDLDLLD LLLUUU RRDDDRD   LDULULDL DLDDLL DLLL LRUU   DDDRRDD UDUDL   ULURU DDDDR RDRR DUL   DRR UUURURRU LLLD   RUURR UULLLUUU RRRRUURU   LDUDUUD DRRR LU DRRRDRR LRU   DRDRD DLLDDD RR LRD DLDDLLDL   DDRDD LLLLUU   UUUULLU URRUUUUR   UDRR RDDDD DRRRRDR   RUU LLDD LLDLLDLD RRRDUUDRDU   DRR DRLDDD RDDRRDD   RRUUR UL LLLDDLDLDD   UUUULLL RDDRDDD DDRDDRDR URDDURRR DDLLDLLD   DRDDD DUUDULD.
L      o         o         k     ,  a    l      l      I      'm      s        a      y    i       n        g         i       s    ,  w       h   a       t      h    a      r       m         i       s       t     h  e        r       e            i       n       a       s    k        i       n     g      ?  T    h        e          h        a    r        m            i       n          a   s     k      i       n       g            i       s      t    h    a   t      T    o    m     w   i       l      l            s     a       y         n     o        .  W     e     a      s        k        f     o  r         f   o         r       g       i       v     e        n        e        s    s    ,  n          o      t       p      e        r        m    i       s        s     i       o      n       .  A    n     d         i       f         t    h    i       s      s t    o         r       y   's          a   s       g           o    o    d        a       s      I   t    h        i       n        k        i       t   's       g   o         n      n      a        b  e  ,  t    h        e        n       T    o         m            w   o        n     't      c     a    r        e       .  I     n   fact, he'll thank us. Or the old lady is nuts and the story blows up in our face and Tom fires us.
```

The error became apparent in this process around this point.
```
RDRDR DDLL RDRRDDDD URURRRUR.  UURRR LD LUU   RRD LUUUR L RURU R
c     a    r        e       .  I     n   fact, he'll thank us. O
```

As determined by the double space, after the sentence ending with "care.", a three-letter word is expected, however 
the quote only has a two-letter word.  As such, back to manual decoding of the commands. 

```
UURRR LD LUU   RRD LUUUR L RURU RRRR DRDRRRR   RDDDDRD ULLUL   RDDRDRDR LU DLDRDLRDRL LLLULLU RUR ULUULUU.
the answer is konami.
```

Submitting the flag of `konami` indicated a correct answer.

## Lab Homework
### Clue
```
One of the sensors on the Hawkins National Laboratory’s public facing dashboard is displaying some weird unreadable messages. Can you take a look?

Dashboard: 54.80.132.176
```
### Solution
In visiting the IP Address via the web browser we're presented with a dynamically updating dashboard.

![labhomeworkdashboard.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/labhomeworkdashboard.png)

Noticed the "Evil Sensor" with some gibberish displayed, but before tackling that, a review of the HTML/Javascript was 
conducted in an attempt gather context for any other clues.  

Upon looking at the [HTML](https://github.com/SecDSM/secdsm.github.io/blob/main/assets/2021-09-18-corncon-ctf-writeup/LabHomework.html), it was clear that the page was using a javascript library called 
[Eclipse Paho JavaScript client](https://github.com/eclipse/paho.mqtt.javascript) to connect to and receive messages 
from a [MQTT](https://mqtt.org/) server.  The javascript would receive the messages, inspect the messages for which 
sensor it was for and then update the sensor's text on the page. 

In order for this to function, the receiver actually "subscribes" to which "topics", and then declare which function to 
run when new messages were received. 
```javascript
// once we conenct, subscribe to the "sensor" 
function onConnect(){
    console.log("Connected");
    mqtt.subscribe("sensor/#");
}
```

Upon seeing this, the first attempt to find the solution was to subscribe to all topics.  Quickly downloading the HTML 
and correctly "relative" references to the absolute paths which included the remote ip address of the server, the HTML 
page could be rendered and modified locally.  This allows for a quick development environment where the code could be 
manipulated without running a webserver or any other software beyond a web browser.   

After quick DuckDuckGo, and a primer on [MQTT topic levels](https://www.hivemq.com/blog/mqtt-essentials-part-5-mqtt-topics-best-practices/) 
subscribing to all the topics was a quick change.
```javascript
// once we conenct, subscribe to the "sensor" 
function onConnect(){
    console.log("Connected");
    mqtt.subscribe("#");
}
```

However, nothing new was presented.  After learning a bit about MQTT and gaining all the context of how the dashboard 
was working, attention was focused back on the text being displayed on the "Evil Sensor"

`Prxwkeuhdwkhu`

One very useful item for determining if a key based encryption is used, or a more simple substitution/rotation cihper is 
to examine the [entropy](https://en.wikipedia.org/wiki/Entropy) of the string.  Given this string is 13 characters long, and we suspect the flag would be in the 
English letters.  Thankfully, [CyberChef](https://gchq.github.io/CyberChef/#recipe=Entropy('Shannon%20scale')&input=UHJ4d2tldWhkd2todQ) 
has a recipe for this, and we can quickly get this.   

Entropy pretty much measures out "random" something is on a scale of 0 (no randomness) to 8 (perfectly random). 
Encryption creates randomness, substitution/simple rotations don't change the "randomness" of a string.  

CyberChef shows the Shannon Entropy for this input at 3.0, petty darn low. This leads the direction of not being a 
keyed encryption method.  A good first guess is something like 
[Caesar Cipher](https://en.wikipedia.org/wiki/Caesar_cipher) and it's friend ROT13.  

In this case, CyberChef can also be used to "roll though" the different shift options and some clear text is found at 
ROT23

![labhomeworkdashboard.png]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/labhomeworkdashboard_solve.png)
```
Mouthbreather
```

Coming back to Entropy for just a bit.  It's an interesting concept with a boatload of uses within information 
security. I went back with our answer and ran it through a few different methods just to see what the Shannon Entropy
would be for them. 

|Method|Entropy|
|------|-------|
|[Plain Text](https://gchq.github.io/CyberChef/#recipe=Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|3.085|
|[ROT23](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,23)Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|3.085|
|[Single byte XOR](https://gchq.github.io/CyberChef/#recipe=XOR(%7B'option':'Hex','string':'0a'%7D,'Standard',false)Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|3.085|
|[Vigenère](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Encode('corncon')Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|3.335|
|[Multiple bye XOR](https://gchq.github.io/CyberChef/#recipe=XOR(%7B'option':'Hex','string':'9285810f81970eeeb109010d47a05ea5'%7D,'Standard',false)Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|3.700|
|[AES-ECB](https://gchq.github.io/CyberChef/#recipe=AES_Encrypt(%7B'option':'UTF8','string':'0123456789abcdef'%7D,%7B'option':'UTF8','string':'0123456789abcdef654654'%7D,'ECB','Raw','Raw',%7B'option':'Hex','string':''%7D)Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|4.0|
|[AES-GCM](https://gchq.github.io/CyberChef/#recipe=AES_Encrypt(%7B'option':'UTF8','string':'0123456789abcdef'%7D,%7B'option':'UTF8','string':'0123456789abcdef654654'%7D,'GCM','Raw','Raw',%7B'option':'Hex','string':''%7D)Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|5.11|
|[RSA 1024bit Key](https://gchq.github.io/CyberChef/#recipe=RSA_Encrypt('-----BEGIN%20PUBLIC%20KEY-----%5CnMIGeMA0GCSqGSIb3DQEBAQUAA4GMADCBiAKBgGheVAQz7fjaPxMk3%2BlNQN5KM4Yy%5Cn5d3DeOUGfJKYuGgAquBnAZ/y/2E%2BBwbE8eq1zbsHQ%2B2s60EzB7AHgABGKElitx4i%5CnfUCD8yjs9yKs1cEf10TV4S/viSR9Hg3PpjNOSWxirVvvBgtY2/s%2BT82IjxH3mxwU%5Cn%2BTHEQY4YbDTGiTTLAgMBAAE%3D%5Cn-----END%20PUBLIC%20KEY-----','RSA-OAEP','SHA-1')Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|6.560|
|[RSA 2048bit Key](https://gchq.github.io/CyberChef/#recipe=RSA_Encrypt('-----BEGIN%20PUBLIC%20KEY-----%5CnMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEArAElXoHl7xlhEAPBhSHd%5CnzD26dUrV/9siPjQMOwtDFf0N961nQduPX7m0p/QP%2B7kDouEKABd9c5/T1Xz3Ma6h%5CnKZohNf13dbyrMe73iFRVwNjg5DvunIhe2qH3o2jInW3rtSXBU08ki5IYLlmrgzvT%5CnNTs1SpK9WUKsLw%2BJ9DFCJHQO7EyAPbBZkMsA3seNGzmuycdbURC2%2BBkDOfK0tYzF%5CnYc9HHOgtbEKGYCDZ%2BG0x7SmBearZf3Loto6/7W1GIyAxWjPAU6K96TK/8XHUMWzQ%5Cn4dwI79knUT4JJyx9R9/TtRbuEdQo377vDzWQ9i%2BWjg2ElVhJSAxgs2jIMBguBF8Y%5Cn8wIDAQAB%5Cn-----END%20PUBLIC%20KEY-----','RSA-OAEP','SHA-1')Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|7.072|
|[RSA 4096bit Key](https://gchq.github.io/CyberChef/#recipe=RSA_Encrypt('-----BEGIN%20PUBLIC%20KEY-----%5CnMIICITANBgkqhkiG9w0BAQEFAAOCAg4AMIICCQKCAgBoPm1sSsX9Eia5D7ly0BBr%5CnLUwLCMs2s5uetlPZjHcxxTQgaG1fij6QW5QruWKHQJukOQIsIaKAazaANb5m7lX8%5CnBqvFWwhC1DMnQ81feFFw8IIuX2aGaZnku6Q5z2dv6jO2e4Dtx4DLPHA/8L8sZwI0%5CnScuYH7ddfgI38AqIkt4e5FZqnVIK%2Bei3hLxaUS%2Bp7RbPKLivE9oBSsv32z7j3RFH%5Cn5LS986xRs5Swro0DDHxxUi4o74HFI7ZjFrc%2BgTfVabL/Swsdzsk/FD3MKAk3Iub8%5CnwHdKuD8nBNE2hd9FxRTbpM6Y0/a9mPvPY9Fclk2gXlm60SDYRkoFvAu0qB0VpWGB%5CnypvgHOiDz6okauwYPrpfpZyoqL%2Bfz9td8mha858TXsaUAdhkGn2Wc%2BD0n0SxgXNj%5CnL6rcs3YgxWj9qkdKOp6qtyPtTG9TCZf8c05WbAVJXCH0aKjbwjTRJn5B%2BncTMuZw%5Cnw/DxQv6sYNjHKAGIFHCoCijM37e8d26moToUMVClRV%2BLlNhvFCF058Aih5T%2BWx0T%5Cn1ONPOnLmQyvH1QpAT6dGSKNifDvw42JP70fuftclda7znLt8B4oinFoJdGsmH0vJ%5CnZidgbCrKJ/IjXIZvVWwM8S3UEwKHsJ8POKSsiss29kmxm3F1PL9OCDyqlJQUrOZx%5Cnqj76OcxRza4NT3dYoHlY%2BwIDAQAB%5Cn-----END%20PUBLIC%20KEY-----','RSA-OAEP','SHA-1')Entropy('Shannon%20scale')&input=TW91dGhicmVhdGhlcg)|7.59|


Overall, a very fun challenge with tons of learning opportunity.  Looking forward to seeing this challenge being used 
next CornCon and working multiple challenges into the Dashboard concept! 


## Typo Squatting
### Clue
```
What is in my traffic?
```
### Provided Files
[pcap]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_5.pcapng)
### Solution
TODO

## Don't Blink
### Clue
```
Solve the animated pic
```
### Provided Files
[corncon_7.gif]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_7.gif)
### Solution
TODO

## What's your Vector, Victor?
### Clue
```
Our sensor network detected an anomalous power surge at 1500. We were able to calculate the source to a location just behind Hawkins Library.

Please use the data to help us calculate where the power spike occurred at 0330.
```
### Provided Files
[Hawkins_Map.jpg]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/Hawkings_Map.jpg)
[hawkins_stats.csv]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/hawkins_stats.csv)
### Solution
TODO 

## Junior Panda Swim Team
### Clue
```
Solve the text

```
### Provided Files
[corncon_4.txt]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_4.txt)
### Solution
TODO

## Influencer
### Challenge
```
I was driving through town making a video for my YouTube channel and I heard something wierd come across the radio...

Can you help me figure out what it was? Until then, I'm just going to post the video without any sound.
```
### Provided Files
[corncon_8.mp4]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/corncon_8.mp4)
### Solution
TODO

## Town Square
### Clue
```
We recovered this file from the remains of the lab, but it appears incomplete.

Maybe you can fix it and help us solve the mystery.
```
### Provided Files
[invasion.js]({{ site.url }}{{ site.baseurl }}/assets/2021-09-18-corncon-ctf-writeup/invasion.js)

### Solution
TODO
