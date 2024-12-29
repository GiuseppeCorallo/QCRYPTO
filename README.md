                      **** Check QCrypto_Showcase.mp4 for a small video showcase of the program. ****

___________________________________
ENCRYPT ANY DOCUMENT
------------------------------------------------
With an extremely user-friendly setting you can encrypt text documents, photos, movies, ZIP, encrypt PDF documents, Word documents and any other document.
For example, you can record voice messages (.m4a), encrypt them and send them as email attachments.
You can write a text that is directly encrypted, i.e. there is no clear text version.
You can give encrypted documents any name you want because the name of the source file is stored in the encrypted file and when the document is decrypted its original name is automatically assigned to it.
__________________________
THE ALGOWHEEL ALGORITHM
-------------------------------------
 Let's imagine that around a wheel A there are 170,496 boxes containing all the possible values ​​of 1 byte (0-255) repeated 666 times.

From the 512-bit key a number Y>0 is generated.

By inserting the key the arrangement of the characters in the boxes is changed thus generating a wheel B.

During encryption the wheel "turns" and each character of the original document is found in a specific position P on the wheel.

For example a letter "a" can be found in position 12345 and another "a" in 62005 or the "? " can be in 102385 and also in 12 and in 83950.

In the encrypted file each of these positions will be recorded as X=(P+Y).
When decrypting, once the key is provided, you will obtain wheel B and the same Y.

By making (X-Y)=P you will take all the characters from the correct position to reconstruct the original document.

Even assuming, for the sake of argument, that you have wheel B, but without knowing the key, and therefore not knowing Y, you would still not obtain the original document.  

It is evident that the algorithm is inviolable since no cryptanalysis system can be effective.

A variable number of characters is inserted into the encrypted document, which have no value for encryption purposes but are included in the calculation of the document's NIDE.
This ID Number is a numeric code and, as can be easily seen and verified, the algorithm described above ensures that there cannot be two encrypted files with the same NIDE, except on a purely theoretical level.
Even the same document encrypted with the same key n times will have n different NIDEs.

___________________
AUTHENTICATION
-----------------------------
Each encrypted document contains the NIDE (hash) code.
The encryption system is such that the same document, encrypted n times with the same key, generates n encrypted files that are always different and therefore n different NIDEs.
To see the explanation in the folder you will find the encrypted file ALGORUOTA.Q
Import the key from KIMPEX with function 5 and then decrypt it.
This property of the NIDE is the digital signature of the document as it guarantees its origin, authenticity and integrity.
Furthermore, the NIDE has a decisive role in ensuring security during the key exchange process (see KEY EXCHANGE)
The NIDE is shown at the end of the encryption, checked by the system before decrypting the documents and can be verified at any time with a special function that also shows
- name of the key used
- who and when encrypted the document
- name of the original document
_________________
THE KEY FILE
-----------------------
When you use it for the first time, you are asked to set a
64-character passphrase (FK).
All your keys are stored in an archive and are encrypted with this FK.
So you have 2 advantages:
- you don't have to remember all the keys you use, which would be very difficult since they are all almost exclusively made up of special characters
- you don't have to find a safe place to hide them
It's like having many safes, you can't go around with all those keys, so you put them all in a drawer and you only have to carry around the key of that drawer.
FK is the only key you have to remember because you need it to enter the system and without FK you could no longer recover your encrypted files.
The key archive contains all the keys in the form:
KEY NAME (in clear, anyone can see it) + KEY (that only you can see, because it is encrypted with FK).
To encrypt, you indicate the name of the key to use and this is taken from the archive, decrypted with FK and used for encryption.
So to decrypt, you just indicate the name of the encrypted document.
The name of the key is stored in the document and the key is taken from the archive.
Keys can be generated using the appropriate function of the program and assigning them the desired name.
A shared key can be created with a correspondent with the key exchange procedure (see KEY EXCHANGE).
A key can also be imported into the system or exported.
__________________________
KEY EXCHANGE
-----------------------------------
They can be generated using the program's specific function and then assigning them the desired name.
You can create a shared key with your correspondent with the key exchange process.
The process takes place in 2 stages:
A ----------- data ---- »B which generates a key K
B ----------- data ---- »A which generates a key = K
The name is the correspondent's user name, it is assigned automatically and allows both to correctly decrypt
the messages as on each encrypted file that will be exchanged there will be the name with which the shared
key was inserted in the key file.
The program shows which phase is in progress.
You just have to agree on who starts phase 1.
A description can be associated with the keys created to facilitate the identification of a correspondent.
A key can also be imported into the system via a file with name KIMPEXP that has the following format: key
name (24) + username (24) + key (64)
The function that generates the keys allows you to export the
generated key to the KIMPEXP file. With the camouflage function you
can put KIMPEXP inside a photo to be sent to your interlocutor and
thus make a reasonably safe key exchange. The interlocutor will do
the decamouflage and import the key from the KIMPEXP extracted
from the photo. it is possible to make a list in which all keys are
shown (some special characters which are not viewable are replaced
with ?).
IMPORTANT: Never enter a new key that has the same name as your
nickname. 
How the keys are: 
 
ANOTHER EXAMPLE:
-------------------------
A puts the necessary data in the KEYSCAMB file, encrypts keyscamb with any key Y and sends the encrypted file and Y to B.
B verifies the NIDE with A and if it is ok, decrypts keyscamb with key Y, then creates the key KB, puts its data on keyscamb, encrypts it with Y and sends the encrypted file to A.
A verifies the NIDE with B and if it is ok, decrypts keyscamb with key Y, then creates the key KA=KB
Now let's see what X could do.
It intercepts the key Y and keyscamb sent by A.
It can decrypt it and create a key KX, put its data on keyscamb,
encrypt it with Y and, let's suppose that it can replace the keyscamb sent by B to A with its own keyscamb and thus wants to replace B.
But it fails in its intent because once A and B have verified that their NIDEs do not match, they will discover the intrusion attempt. In fact X has replaced keyscamb, but the NIDE of its keyscamb cannot be the same as that of B.
__________________________
CAMOUFLAGE AND UTILITIES
------------------------------------
With the camouflage function you can hide a document A inside a document B.
B remains available for any application, that is, if B were a photo it would be seen exactly as before.
With the decamouflage function you extract A.
It is possible to change the language. The languages ​​now possible are IT, EN, CZ and DE.
You can physically delete a document and in the case you want to transmit a really large document and you do not have other tools (think of a film of many Gigabytes) then you can divide it into many segments of the desired size and then reconstruct the original document from them.
____________________
USING THE PROGRAM
---------------------------
To have a good layout:
- create a Qcrypto link icon on desktop
- right click on link icon
- properties / layout
- in window dimensions set 30 in height and 102 in width
