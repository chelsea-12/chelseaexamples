# H4 Encryption


## Summaries


### Applied Cryptography


### Disobey 2023


## Encrypt and Decrypt


I referred to [Tero's Guide](https://terokarvinen.com/2023/pgp-encrypt-sign-verify/) to try out PGP (Pretty Good Privacy) within Linux by simulating two users. PGP is a security program used to encrypt and decrypt email and to authenticate email messages through digital signatures and file encryption. PGP was one of the first public-key cryptography softwares publicly available for free [(source)](https://www.fortinet.com/resources/cyberglossary/pgp-encryption).

After installing the required tools I went ahead and generated a key.

![Public Key](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-08%20140359.png)

I exported my key, which looks like this:


![key](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-08%20141556.png)


Then I went ahead and set up my second simulated user, Alice, by inputting this into the command line.

>$ cd<br>
$ mkdir alice/<br>
$ chmod og-rwx alice/<br>
$ cd alice/<br>
$ gpg --homedir . --fingerprint<br>
gpg: keybox '/home/tero/alice/pubring.kbx' created<br>
gpg: /home/tero/alice/trustdb.gpg: trustdb created<br>
$ gpg --homedir . --fingerprint

While within Alice's directory, I created a key for her, and then transferred my public key (chelsea.pub) into Alice's directory (simulating just showing Alice this key, seeing as it is a publicly available key). As Alice, I went ahead and verified the key as trusted.

![trusted key](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-08%20144401.png)


I then imported Alice's key (alice.pub) and verified it myself. Now both Alice and I have eachothers public keys so we can send messages to one another and sign them to ensure we know the message has been sent by that person. As Alice, I wrote a plain text message and encrypted it, ready to send. It was at this point that I realised I made a mistake, as I had initally started this exercise using Tero's example literally and then changed my mind half way through and made a new e-mail address. At this point I realised it would be easier just to stick with Tero's email address as this was what I created first, and I was having issues with establishing the trust towards Alice.

![encrypted message](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-08%20150022.png)

I then transferred the file, to simulate sending it, and used the command line to decrypt the message. Everything went well!

![Decrypted Message](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-08%20151620.png)

You can see here Tero's email address rather than the other e-mail address in the previous screenshots.



## Cracking Cyphertext

>HDMH'B TH. KWU'YI AWR WSSTOTMJJK M OWQINYIMLIY! MB KWU BII, BTGPJI BUNBHTHUHTWA OTPDIYB OMA NI NYWLIA RTHD SYIEUIAOK MAMJKBTB. BII KWU MH DHHP://HIYWLMYCTAIA.OWG

I cracked this text in Microsoft Word. I started with the most obvious characters - in the first word this was guessing that the B after the apostrophe was likely an S. Whereas in the third word the two letters after the apostrophe were most likely RE. Near the end was a website address so through deciphering the HTTP, I got a few more letters revealed. I continued to work systematically like this and the more letters I revealed, the more words I was able to guess.

![Deciphering the text](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-08%20104432.png)

The final result was:

>THAT'S IT. YOU'RE NOW OFFICIALLY A CODEBREAKER! AS YOU SEE, SIMPLE SUBSTITUTION CIPHERS CAN BE BROKEN WITH FREQUENCY ANALYSIS. SEE YOU AT HTTP://TEROKARVINEN.COM
