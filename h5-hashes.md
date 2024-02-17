# H5 Hashes


## Summary


### 2.3 One-Way Functions


- one-way functions are relatively easy to compute, but significantly harder to reverse (similar to smashing a plate)
- this is not so helpful when we think of encryption and decryption
- a trapdoor one-way encryption is a way to get around this: easy to encrypt and hard to decrypt unless you know the secret to compute the function in the other direction


### 2.4 One-Way Hash Functions


- one-way hash functions are central to modern cryptography
- this is a function (mathematical or otherwise) that takes a variable-length input string (pre-image) and converts it to a fixed-length output string (hash value)
- simple hash function takes a pre-image and returns a byte consisting of the XOR (Exclusive or) of all the input bytes
- the point here is to fingerprint the pre-image
- a good one-way hash function makes it hard to generate two pre-images with the same hash value
- hash function is public as the secrecy comes from the one-way approach
- a MAC (message authentication code) is a one-way hash function with the addition of a secret key
- theory is the same as a hash function except only the person with the key can verify the hash value


[SOURCE](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003)


## Installing Hashcat & Cracking a hash


I followed Tero's tutorial [here](https://terokarvinen.com/2022/cracking-passwords-with-hashcat/) to install and try out Hashcat on my Linux computer. After doing my general update of apps, I entered this command to the command line in order to install hashcat:


>sudo apt-get -y install hashid hashcat wget


I followed that up with creating a new directory for me to work from:


>mkdir hashed<br>cd hashed


Now that it's all downloaded and I've created a directory, I next downloaded a password dictionary containing over 14 million possible passwords, called 'rockyou'. This will be the best basis to try and crack a password hash.


![Hashcat](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-17%20143735.png)


I tested out hashcat using a simple hash provided by Tero. MD5 is a very common hash type, and so is the only hash type I have tested hashcat out with. Within Hashcat this hash has the mode 0 related to it, so to try and crack the hash we insert (the string of numbers and letters is the hash):


>hashcat -m 0 '6b1628b016dff46e6fa35684be6acc96' rockyou.txt -o solved


The result is saved into a file called 'solved'. Hashcat tells us we have been successful in cracking the hash, so then we open up the 'solved' file to get the result.


![Hash 1](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-17%20144057.png)


The password is 'summer'. Next up I tried another hash in the MD5 type. Here I will provide a series of screenshots, so you can see how I did it.


![cracking a hash](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-17%20144633.png)


![hash is cracked](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-17%20144650.png)


![solution](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-17%20144701.png)


The answer is 'february'.


## Password Manager


[Forbes](https://www.forbes.com/advisor/business/software/best-free-password-manager/#:~:text=The%20Best%20Free%20Password%20Managers%20of%202024%201,for%20programmers%205%20LastPass%3A%20Best%20single-user%20password%20manager) lists these as the top five free password managers in 2024:


>Norton<br>Dashlane<br>Bitwarden<br>KeePass<br>LastPass


Norton is listed as the 'best overall', so I decided to take a closer look at that one.


Norton is installed as a browser extension, so I installed it on my Firefox browser straight from their website. This was a very quick and easy process.


![Norton](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-17%20152050.png)


I then needed to create an account, and set up a vault password.


![Norton set up](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-17%20152424.png)


Within minutes I was able to test it out and set up my first password. I navigated to app.terokarvinen.com and put in my log in details. Then a new window from Norton popped up asking if I wanted to save this password to my vault.


![Password](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-17%20153002.png)


I was immediately able to view it in my Norton dashboard.


![Norton Dashboard](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-17%20153033.png)


Password managers help you to keep track of a number of different passwords for different logins - this way you should be able to choose unique and hard to guess passwords for every single login, rather than reusing a password for multiple logins. Therefore they protect against the threat of hackers guessing your passwords, or finding out a password from an easy to hack website and then using that password to try and log into higher security websites (e-mail, bank accounts etc.). <br>
In addition to that, Norton will also look through the dark web for any password leaks and notify you if any of your passwords show up.<br>
A password manager will automatically fill in your log in details on recognised websites - therefore if you click a phishing link which takes you to a false website, it will not fill in your details there. Furthermore, automatically filling in a password can help protect you from the threat of keyloggers which monitors your keystrokes.


The encrypted information is the password and usernames, whereas unencrypted information includes modification dates, country code for address formatting, favorite markings, and password hints. These are unencrypted for necessary functional purposes.


Norton Password Manager is free, and only required that I set up a free account with Norton. This password manager is cloud based, and Norton maintains their own clouder servers all around the world.


Data is encrypted with 256-bit AES encryption, basic two-factor authentication and TLS secure connections. No Norton employee is able to access your passwords, and the unencrypted data is only viewable by you. The use of a master password can be an issue however - if you forget this password there is no way to retrieve it. Similarily, if someone were to guess you master password, they would then have access to your password vault.


SOURCES:<br>[Forbes](https://www.forbes.com/sites/forbestechcouncil/2022/01/20/are-password-managers-safe/)<br>
[PC Mag](https://uk.pcmag.com/password-managers/117939/symantec-norton-password-manager)
