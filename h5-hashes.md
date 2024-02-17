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





## Password Manager
