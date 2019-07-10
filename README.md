# waitingoutmail
_waitingmail_ is a simple (ha!) bash script to monitor a FTN<sup>1</sup> BSO<sup>2</sup> directory structure used by FTN mailers to send waiting mail to other FTN systems.

currently _waitingoutmail_ expects a 5D directory structure where each secondary FTN domain has its own outbound directory and each directory has an extension representing the HEX value of the FTN's zone. this depends highly on how your FTN mail tosser creates and manages the BSO. Both tosser and mailer must work together or mail will not be transported as desired.

eg:<br/>
1st FTN address: 1:123/456@fidonet<br/>
2nd FTN address: 27:321/654@foobar<br/>
3rd FTN address: 432:987/345@riptide<br/>
4th FTN address: 999:76/785@yanknet<br/>

/bbs/ftn/out/fidonet<br/>
/bbs/ftn/out/foobar.01b<br/>
/bbs/ftn/out/riptide.1b0<br/>
/bbs/ftn/out/yanknet.3e7<br/>

1. Fidonet Technology Network<br/>
2. Binkley-Style Outbound
