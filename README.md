# waitingoutmail
waitingmail is a simple (ha!) bash script to monitor a FTN (Fidonet Technology Network BSO (Binkley-Style Outbound) directory structure used by FTN mailers to send waiting mail to other FTN systems.

currently waitingoutmail expects a 5D directory structure where each secondary FTN domain has its own outbound directory and each directory has an extension representing the HEX value of the FTN's zone. this depends highly on how your FTN mail tosser creates and manages the BSO. Both tosser and mailer must work together or mail will not be transported as desired.

eg:
- 1st FTN address: 1:123/456@fidonet
- 2nd FTN address: 27:321/654@foobar
- 3rd FTN address: 432:987/345@riptide
- 4th FTN address: 999:76/785@yanknet

- /bbs/ftn/out/fidonet
- /bbs/ftn/out/foobar.01b
- /bbs/ftn/out/riptide.1b0
- /bbs/ftn/out/yanknet.3e7
