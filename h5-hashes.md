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


## Installing Hashcat & Cracking a hash


## Password Manager
