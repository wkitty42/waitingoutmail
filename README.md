# waitingoutmail
_waitingoutmail_ is a simple (ha!) bash script to monitor a FTN<sup>1</sup> BSO<sup>2</sup> directory structure used by FTN mailers to send waiting mail to other FTN systems. its purpose is to provide a human readable listing of mail waiting for delivery, what the mail consists of, and how long it has been waiting.

currently _waitingoutmail_ expects a 5D BSO directory structure where each FTN domain has its own outbound directory and each FTN domain's directory, except the one for your main FTN address' zone, has an extension representing the HEX value of the FTN's zone. this depends highly on how your FTN mail tosser creates and manages the BSO. Both tosser and mailer must work together or mail will not be transported as desired.

in the following example, the 1st FTN address is the main FTN address. all others are AKAs<sup>3</sup>. the main address' outbound has no extension on it while each of the others do.

for example, if you have the following FTN addresses in the given FTN domains:
```
1st FTN address:   1:123/456@fidonet
2nd FTN address:   1:888/923@treknet
3rd FTN address:  27:321/654@flubber
4th FTN address: 432:987/345@riptide
5th FTN address: 999:76/785@joesnet
```
you will start off with a BSO structure like this:
```
/bbs/ftn/out/fidonet
/bbs/ftn/out/treknet.001
/bbs/ftn/out/flubber.01b
/bbs/ftn/out/riptide.1b0
/bbs/ftn/out/joesnet.3e7
```
fidonet contains zones 1 through 6 so mail for systems in fidonet zone 2 will be placed in ```/bbs/ftn/out/fidonet.002```
and mail for fidonet zone 3 will be placed in ```/bbs/ftn/out/fidonet.003```.

note that treknet duplicates zone 1 in its structure. with a full 5D BSO, treknet mail will be placed in its own treknet BSO subdirectory as shown above. this is the only way to prevent zone collisions between FTN domains.

once mail for fidonet zones 2 and 3 has been generated, the BSO structure will look like this:
```
/bbs/ftn/out/fidonet
/bbs/ftn/out/fidonet.002
/bbs/ftn/out/fidonet.003
/bbs/ftn/out/treknet.001
/bbs/ftn/out/flubber.01b
/bbs/ftn/out/riptide.1b0
/bbs/ftn/out/joesnet.3e7
```
one last item to note is that FTN domains are limited to 8 characters. that's all the room there is allocated in the binary PKT file headers. there are no dots or other punctuation allowed. dashes are permitted but not underscores.

as you can see, a 5D BSO is fully capable of handling duplicate zones across FTN domains. we cannot stress how important it is that this is all dependent on how your mail tosser manages the BSO directory structure. both the mail tosser and the mailer have to be able to work together in the same manner or there will be problems with mail being sent to the wrong systems if it is even sent at all.
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

---

1. Fidonet Technology Network<br/>
2. Binkley-Style Outbound<br/>
3. Also Known As
