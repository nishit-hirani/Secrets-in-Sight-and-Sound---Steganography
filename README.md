This project enables hiding messages within various types of files (images, text, audio, and video). The sender selects a cover file and embeds secret text within it using efficient algorithms, creating a stego file of the same format. The stego file is then transmitted to the recipient through communication networks. Upon receiving the stego file, the recipient decodes it using the appropriate algorithm to extract the hidden secret text.

In the sample folder keep adding the sort of data you would want to hide the data behind and then choose from the switch case options given by the program.


#Image Steganography ( Hiding TEXT in IMAGE )
In this sneaky hiding technique, we take a picture and change the tiniest part of its color information (the least important bit) to store a secret message. We do this one color channel at a time, working with red first, then green, and finally blue. To mark the end of the message, we add a special signal like a secret handshake. This lets the decoder know when to stop looking for hidden bits.
