# H4 Encryption


## Summaries


### [Applied Cryptography](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006)


- a message is referred to as **plaintext or cleartext**; the process of disguising the contents of this message is **encryption**; the disguised message is referred to a **ciphertext**; the process of turning ciphertext back to plaintext is called **decryption**; the art of keeping messages secure is referred to as **cryptography**
- cryptography also refers to authentication (not allowing an intruder to masquerade as someone else), integrity (the message should not have been tampered with or replaced in transit) and nonrepudiation (a sender should not be able to falsely deny they sent a message)
- modern cryptography generally uses an encryption and decryption key (sometimes this is the same key, and sometimes this is two different keys)
- **cryptanalysis** is the science of retrieving the plaintext of an encrypted message without access to the key, and an attempted cryptanalysis is called an **attack**
- the four general types of cryptanalytic attacks are: ciphertext-only attack, known-plaintext attack, chosen-plaintext attack and adapative-chosen-plaintext attack
- the different categories of breaking an algorithm are: total break (the key is found), global deduction (an alterante algorithm is found), instance/local deduction (plaintext of an intercepted ciphertext is found), and information deduction (some information about the key or plaintext message is found)
- stenography is the art of hiding messages within other messages, so the existence of the original message is not even known
- substitution cipher is when each character in a plaintext is substituted for another character in the ciphertext (Caesar cipher is the most famous example of this, the letter is replaced by the characted three to the right, eg. A replaced with D, B replaced with E)
- a transposition cipher is when the plaintext remains the same but the order of the characters is shuffled


### [Disobey 2023 - Don't Trust The Link](https://www.youtube.com/watch?v=iluhSh4E2r8)


- a talk by Marcus Lehtonen who works for CGI managing the Security Operations Center (SOC)
- URL scanning - scanning for suspicious or malicious URLs and is used to fight against phishing e-mails (if something suspicious is found, the link is either blocked or an alert given to the user)
- urlscan.io is a website where these scans can be done (remember this is a public website and scanning a URL here wil then make the URL publicly known)
- a lot of people have done searches on this website, oftentimes these are sensitive links from within the business they are working for
- there is a search function on the website where you can look at all previously searched websites
- information has been leaked via this website (i.e. company details, contents of secure mail, Teams meeting links, or people scanned a link from an email and then through this website a second party has clicked the link and this results in the original person being unsubscribed from a mailing list)
- other notable leaks from this website is leaked URLs from a OneDrive which then allows anyone to access sensitive material that has been shared from OneDrive
- an issue with email links is that they are used a single factor authentication; there needs to be additional layers of authentication for better protection
- how to avoid leaks like this: don't include any sensitive data in URLs, don't assume the avreage user knows how to add security, model the threats
- websites like urlscan.io need to have responsible disclosure


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



## Cracking Cyphertext (extra task)

>HDMH'B TH. KWU'YI AWR WSSTOTMJJK M OWQINYIMLIY! MB KWU BII, BTGPJI BUNBHTHUHTWA OTPDIYB OMA NI NYWLIA RTHD SYIEUIAOK MAMJKBTB. BII KWU MH DHHP://HIYWLMYCTAIA.OWG

I cracked this text in Microsoft Word. I started with the most obvious characters - in the first word this was guessing that the B after the apostrophe was likely an S. Whereas in the third word the two letters after the apostrophe were most likely RE. Near the end was a website address so through deciphering the HTTP, I got a few more letters revealed. I continued to work systematically like this and the more letters I revealed, the more words I was able to guess.

![Deciphering the text](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-08%20104432.png)

The final result was:

>THAT'S IT. YOU'RE NOW OFFICIALLY A CODEBREAKER! AS YOU SEE, SIMPLE SUBSTITUTION CIPHERS CAN BE BROKEN WITH FREQUENCY ANALYSIS. SEE YOU AT HTTP://TEROKARVINEN.COM
