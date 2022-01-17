**Day 26 - A Final Challenge**

What a Christmas this has been! You of course managed to save it by recovering the sleigh keys just in time, but then you had to spend two entire weeks in a decompression chamber upon your return from the depths of the ocean. But that’s all behind you: Once the large seven-segment display-style countdown timer in the chamber had ticked down to zero, you had only one plan: A nice, long and well-deserved vacation. You’re just getting comfortable as the

**ADVENT**

(the **A**mazing **D**evice for **V**ery **E**xciting **N**orth Pole **T**ransmissions of course), a thank-you gift from Santa himself, in your pocket starts to beep repeatedly. “What now?”, you sigh, activating the screen.It looks like you have received a set of encoded messages from all over the world, forwarded to you from North Pole HQ (**your attached puzzle input**).Wondering what this could be about, you try to remember what you’d been reading in the transmission protocol manual to pass the time in the chamber:

- Santa’s preferred method for receiving wish lists is via secured and encrypted message.
- Everyone who made Santa’s list has a unique encryption key which they use to encode their message before it is sent.
- Santa and his helpers hold the respective decryption keys and are able to decipher the message again.
- Keys are comma-separated sets of numbers, and all encryption and decryption keys have the same length.
- For extra security, keys become more complex each day during Christmas time up until Santa starts to travel.

Turns out, the ADVENT actually comes with a digital version of the manual and a few samples (below) of encryption and decryption keys (separated by a space).

```
8,5,8,15,13,8,14,10,31,7,3,43,6,16,12,5,10,7,6,8,24,27,18,9,13 5,4,8,11,8,14,11,28,10,2,3,37,7,5,7,13,11,8,21,9,14,18,16,8,12
205,72,220,49,45,41,19,18,32,11,18,24,35,20,3,42,21,18,30,14,14,44,31,-1,-1 205,106,194,49,38,31,24,23,24,16,21,22,27,15,11,37,18,39,-1,25,13,31,31,-1,-1
316,285,234,136,100,114,120,58,89,64,56,58,56,51,33,47,34,19,23,26,45,41,30,-1,-1 298,273,204,124,89,86,112,32,64,58,55,54,53,36,29,43,32,16,18,20,28,26,26,-1,-1
12,8,12,6,2,7,5,21,4,1,27,59,20,32,11,35,11,-1,-1,-1,36,10,16,-1,-1 11,6,2,3,1,2,2,8,7,5,26,55,14,22,19,31,13,-1,-1,-1,-1,-1,-1,-1,-1

```

Now, of course you know your own encryption key (it’s what you’ve been using to send your wish list after all!), but it looks like you will need a decryption key to decode these messages. Luckily, the ADVENT in its newest version has live access to **[The Christmas Database](https://aoc.lewagon.community/)**. You wonder if there is something in there to help you find the keys…***What is the product of the elements of your own decryption key, first of all?***

**Some comments:**

- This puzzle is primarily a thank-you for [@Pilou](https://lewagon-alumni.slack.com/team/URZ0F4TEF) for everything he's done for this community, but anyone can play of course. Please avoid any spoilers in the thread; best to wait to post/validate your solution until [@Pilou](https://lewagon-alumni.slack.com/team/URZ0F4TEF) has finished the challenge (no pressure, bud...). If you have a general question and are unsure if it could be a spoiler, use an appropriate **`SPOILER`** tag please, or send a DM.
- I'm not Eric Wastl, and also didn't have months to prepare the puzzle (big thanks to [@Guillaume](https://lewagon-alumni.slack.com/team/U0223TXTXDW) and [@aquaj](https://lewagon-alumni.slack.com/team/U0J5GUEAW) for the testing and very helpful feedback!). This *should* work! If not, or if there are ambiguities, sorry in advance. I hope there will be at least a couple of learnings in there.
- Yes, there is a part 2...

# INPUT

```
391: F-bhem-LVRpx-u-RxC-LCiR-u-k9';8#-ZhHC/PCVm-BzAhe(-cC-pVdoR-cVzR-Rh-xhiR-bhe-zd-g0Z(-Rhcd-h
312: XXrSrbfUFGrOFHLTIGFrUGTèGSOOFGqESvRrjTfrJLXTfrÇTGrèLéLvèrOFrSrGFSbTvrÇTGrèFQQLvèr2SIRrLvrQTfIErgLQErOjr2SQIEOSQFbdddrSvHrÇTGrOSRLvèrOFrÇSIFrQEFrÇSIQrQESQr7COrbQL
549: gSOXàPFGPbIqqVPéHFSAG9OPMOqvgCPXHFSAPàvgPèvJPXFAOS2PXHIPXOWIPXvP5gOqKPXHOGPZqFXèvJWPèvJP3:UPpDwVP XpGP5IISPJIFqqàP2vvKPègSPFSKPFP2JIFXPqIFJSOS2PvZZvJX
710: G4'G4) 9Iéq22 q;G4'G21kGlGKÇq' 8
507: P#qw:#/Vq:q-(.'qk iquq? V:Sq#Tq#!:nq wq!/ ,q/. eqd qss:q/ dqè. so)q. eq!?:-rà/:#eqwu#?q wq\/:,/ dqV?o!  Tqàààw?#
17: phs4sQSvbTSEsglsLzFAdsLvITQWsvèlzMsbSFzbgIlTdsFlLNQSJIMWsvTEsFlTFSNMgsMAvMsFlLSszNsvsQlMsfIMAsIMstO1édsR1édsRI:ygMbvsSMFphs?IgAITÇsWlzsvTEsWlzbgsSMSbTvQs:lWsvTEsAvNNITSggsvTEs4sQllysZlbfvbEsMlsTSJMsWSvbVgsàlK8vTWsMAvTygsZlbsITMblEzFITÇszgsMlsàlKst4sAvEsTlsIESvsIMsfvgsvsMAITÇsèSZlbS
305: /\Yuc53\-hchwk3cek\3kuc3n-t3chY(3c \YD3A37Cch\#dd-D3l\h(-nl3kuc3ckkd3-c3kd-ok(Y3oY(3ch37c\kBk3ohuc3n-t3#ZihP3o
660: 9\';Y!-jw9 #j/Ir-!/#-j-!\9#-jkY- oja-:j\9 a- #:j/-jD9#/-; ojÇT-#\Yj(Ya9 jw9 #j\-jx9!jk9k-!néj-njw9 #ja-j:Yn-jF Yj#-!/ja;j\9kwInYnY9!j-!\9#-jwa :j-o\Yn;!n-jÇj)Yc-k-!nja1;!!I-jw#
212: zQKZQzd2dzQKUUézXMZéqWéUUQM2Xz3JKZz2JézXMz2QM2zhKAJZ!QMéUQ2XKZzX2zsXzUKéUzZQ.éXzjXzjéZXRzrz5AQMMdXz3ZJqWQéMXzTzèèYXZqézéM9éMé1XM2zjAQ.JéZzQ33JZ2dz?J0zQKzwQ!JMzX2zjXz1AQ.JéZz9Qé2zjdqJK.ZéZzqXzqWQ55XM!Xyz,QMUz2JéRz1JMz1JéUzjXzjdqX1;ZXzQKZQé2zd2dz;XQKqJK3z35KUz3dMé;5XzX2zsXzMAQKZQéUzsQ1QéUzQK2QM2zQ33ZéUzXMzUéz3XKzjXz2X13Uyz8JMzéMé2éQ2é.Xz1JM2ZXzQKUUézqXzhKXzUé!Mé9éXz5QzqJ11KMQK2dzjKzwQ!JMyz\AXU3cZXzhKXzqX22XzXè3dZéXMqX
249: mnAf\idtm\dA\mEpmmcBb\dA\GAfVcABdSSd\ptA\LVfKfL\lVC\pldz\Id\AVpKlC\ptA\dl\dA\VdmCpB\C\pg\LVfKfL\BdI\tzcg\dm\cdG\PVCtH\ww\cdEfy\fXlEBdi\ptA\Vf\GAfz\AmpO\ptA\
355: SrgLQErSXXrQEFrXSvQFGvÇLbErSvHrHfO2TrTIQTUfbFbrITXXFIQFHrHfGLvèr0TNrcqESvRbrSrXTQrJLXofrÇTGrQELbrèGFSQrXFSGvLvèrTUUTGQfvLQjrSvHrÇTGrSXXTgLvèrOFrQTrFv#TjrbTrOSvjrbfvGLbFbrLvrAFIFO2FGdrWq:rHTrvTQrÇTGèFQrQTrÇFFHrAL#RbQG
253: 1oo)1k#B131p#aV(e(1)(/1rv15)aYr1u:C1Yn'e1iuot1':i1-#(Yx,61u(oi1rso#1':i
323: uXÇ87w(/Xa:mj-:u?(#:'kk?Xawu?:'dX,(X,8X'7hX,(;uXd (D( ?d'7X7u (Xu8kX87aX9'7.X:;sXZ;#87uX (Xa?u,X- ?Xo:;uX;u(.Xu#:  7#X7uXa?.Xu?:'dX?X7,w?X,?.X,:u?o;#u?VXaoX;u(.Xd (u:ko7YXZd (#(u#?'kX 7Xk::9X7uXa?.Xu#:h':kX?X,?.Xu(X5IMQ14;#u?VXu :#:'Xu,7oX:;uXo7'hXu :-8u,X,?X:oX'7xXj#7?X 7d?.X:wX:;uX 7X9'7.X'87aX'7hX;#8oX7,X87aX9 ?;
198: n)x32eouukYCo)/#2x'-2DsV'-2m'k2r)#s/B2ru2Yd)x2)\)#u2'k2\)#s/B2ru2-c2)d2Ç7qX2Y'ru2n)xY32z'kkx2do)d2g2nsn/9d2Ycu/n2r'ku2dsru2'/2V''#s/B2)d2dou2n-rc2x'-2B)pu2ru2y-d2oux62g2\)Y2)Vku)nx2dskun2u/'-Bo242l/x\)x2do)/#Y2)B)s/2m'k2)VV2dou2\'k#2x'-2c-d2'/2dou2Vu)nuky')kn2)/n2d'2r)#u2cu'cVu2u/M'x2n's/B2Y'ru2ck'Bk)rrs/B2upukx2
350: emmoc agro'l ed uaevin ua stroffe set suot ruop icreM .sac tuot ne tejorp uaeb ec rus iot ceva reroballoc ed risialp nu tnemiarv tiaté'C ! siof ettec iarv ed ruop te ,noitidé ettec ruop nif al tse'c ...tse y aÇ ! uoliP tulaSD: orp na'l ruot nu ruop ritraper ed risialp ua te ,edoc ud 
101: 2P-d2Yuks'-YVx62do)/#Y2)2V'd2m'k2s/dk'n-ws/B2ru2d'2lGe32g2o)n2)/2)yY'V-du2yV)Yd2Y'Vps/B2douYu2wo)VVu/BuY62s/duk)wds/B2\sdo2dou2w'rr-/sdx2)/n2)nns/B2msYo2d'2rx2Yosd2VsYd3vs2DsV'-62mskYd2'm2)VV2x'-9ku2\uVw'ru2\u2nsn/9d2r)#u2x'-2Y'Vpu2dosY2)d2é)r4
135: Ç\Sc\LVfAApm\BdI\tzcg\dm\cdG\PVCtHb?LGZd5agdz(BcLgfaakmSAAt\kdAdtS\cdG\PVCtA\mcVdb\)BCpG\ARpV\dA\lBCiBdI\LVfPddE\oVcI\Id\mAdE\lCt\Z\(GAfVcABdSSd\ACpBL\C\tzcm\mCi\Af\pACclCBL\VdLC2\pÇ\ipV\C\mM\)vdM\R\2
326: sfwa8C)u8epY)k8G8 hsAxsrsn8CVsu8)C8ehwkh)y8RuPo))p8arYx8lhsf8xw8G8euw8CP8esf)p8G8CYA8!sxPC8DwxCDPhai8lD)r8lx8mY8eskshrD8y)8euPo8CG8 DY8h)y8Cusfs8ELGWvKv8DPaC8RuPCwshr8h)y8YépPd8PrhsK lCPuYxx)r8sx)Dskw8DPaC8)-k8hwy8DPaC8CsR8)C8spAw8ussA8
503: 6vDnibd6edm\( 6BwkY)6p\(6l\a6\aTkYdndYT6kYs6dYydidYT6(n6i\6iwdn6kVktdYT6h\sdYT6hwkmmDYTD86E6odnw6p\(6k6TaDki6YDo6pDka6éÇéé6kYs6E6w\xD6i\6vD6kvmD6i\6U\dY6ksyDYi6\l6h\sD6odiw6HDNkT\Y6kTkdY86fmm6iwD
109: QGMCXQNM-CmEbèXUCbèèM?AlCMGXJLQbNàCMDGGJyèC7CmÇGMqMèJ6DCKMÇGMÇÇJCKMÇCMOCNEMÇEJLCJèCwCDèEbNDOCÇKMyKCJèMQCMEkCMNaàKMy;CAzCDXODOCFQJèKCMèCNEKCM6JÇNJàCMèCÇMCKMNÇGbQGMNCKMèCMEkCGbXÇXÇDàqbQCJèCÇMCM6JKKXÇGMNààJyèCÇGJÇEJCBMQGMXNDàZMCNMàEKCMGECÇXJÇDyjCmGb6J)Cj/7CEOCGbXÇJKXGJ6NbyèCNEbàCÇGMqDqNbGDCMNb
```

---
**Day 26 - A Final Challenge (Part 2)**

Now that you have obtained your decryption key and a way to get everyone else’s (a security flaw you’ve already alerted the elves to – their reply over **BITS** was “HI”), you should be able to decode the messages. You vaguely remember glossing over some boring rules on how the decryption works – time for a little refresher:

- Messages are encoded using a combination of shifts. Their encrypted length is always the same as the original's.
- A recent update in the encryption system added an extra layer of **SNOW** (**S**uperior & **N**ovel **O**bfuscation **W**rapper): The decryption cipher is actually a combination of the decryption key and the sender identifier:
- If the sender identifier is an even number, it is added to the product of the decryption key sequence.
- If the sender identifier is an odd number, it is subtracted from the product of the decryption key sequence.
- Using the absolute value of the above calculation result, the cipher is the sequence of every third digit, starting from the left.

```
122: 7,2,5,3,4,10,5 6,8,1,2,2,20,2 -> 6*8*1*2*2*20*2 + 122 => 7802 => 72
87: 4,4,3,17,5,6,8 1,3,2,22,4,4,3 -> 1*3*2*22*4*4*3 - 87 => 6249 => 69
40: 12,25,5,-1,4,7,7 18,20,-1,1,5,8,10 -> 18*20*-1*1*5*8*10 + 40 => 143960 => 19
```

- The resulting cipher is then turned into a [ternary number](https://en.wikipedia.org/wiki/Ternary_numeral_system) and processed from right to left. For each trit:
- If the trit is a 1, shift the entire encoded message left by one character (the first character becomes the last).
- If the trit is a 2, shift the entire encoded message right by the trit's magnitude (characters chopped off the end get added back to the beginning).
- If the trit is a 0, reverse the message string.

```
For cipher 46, the ternary representation is 1201. Suppose our string is abcde:
abcde -(shift left by 1)> bcdea -(reverse)> aedcb -(shift right by 3^2 = 9)> edcba -(shift left by 1)> dcbae
```

- Finally, the shifted message characters are decoded using a [Caesar cipher](https://en.wikipedia.org/wiki/Caesar_cipher):
- Get the prime factors of the original cipher (in decimal) and shift each character along the Rudolphabet* by their sum.
- If the cipher is a prime number (i.e. if its only prime factor is itself), add 5 to the value before you shift.
- *North Pole HQ uses a special alphabet called the Rudolphabet. It works almost like the normal alphabet, except that the letter order follows their first appearance in the [popular song lyrics](https://www.41051.com/xmaslyrics/rudolph.html). This includes, separately, lower- and upper-case letters. All remaining letters, punctuation marks, special characters and the space character are ignored and stay at the end. The Rudolphabet repeats over and over; if you have to shift further than its length, simply append the missing characters again.North Pole HQ previously used the [Jinglebet](https://www.41051.com/xmaslyrics/jingle.html), which turned the standard alphabet* `ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyzÇàéè0123456789 .!?,;:'-#/\()` *into `DashingtrouewOplfdLyBbmkWAjJIMFTNGHcCEKPQRSUVXYZqvxzÇàéè0123456789 .!?,;:'-#/\()`.*

```
Using the Jinglebet, for cipher 46, we shift by 23+2 = 25: D becomes A, a becomes j, s becomes J and so on.
```

***Decrypt all the messages you have received, using the respective cipher for each sender.***
