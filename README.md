This project enables hiding messages within various types of files (images, text, audio, and video). The sender selects a cover file and embeds secret text within it using efficient algorithms, creating a stego file of the same format. The stego file is then transmitted to the recipient through communication networks. Upon receiving the stego file, the recipient decodes it using the appropriate algorithm to extract the hidden secret text.

In the sample folder keep adding the sort of data you would want to hide the data behind and then choose from the switch case options given by the program.


# Image Steganography ( Hiding TEXT in IMAGE )
In this sneaky hiding technique, we take a picture and change the tiniest part of its color information (the least important bit) to store a secret message. We do this one color channel at a time, working with red first, then green, and finally blue. To mark the end of the message, we add a special signal like a secret handshake. This lets the decoder know when to stop looking for hidden bits.

# Text Steganography ( Hiding TEXT in TEXT )
This technique uses special characters called zero-width characters (ZWCs) to hide a secret message within normal text. Here's how it works:

1)Encoding the message: Each character in the secret message is converted to its numerical code.
2)Shifting based on type: If the code represents a symbol or punctuation mark (between ASCII values 32 and 64), it's shifted by a certain value. Otherwise, it's shifted by a different value.
3)Scrambling with a key: The shifted code is then mixed up with another number (like a secret key) using a mathematical operation.
4)Adding flags and converting to binary: Depending on the character type, a unique identifier is attached. Everything is then converted into a series of 0s and 1s.
5(Marking the end: A special code is added at the very end to signal the message's completion.
6)Splitting and hiding: The long string of 0s and 1s is broken down into smaller chunks. Each chunk is then converted into a combination of specific ZWCs according to a lookup table.
7)Embedding in cover text: These ZWCs are inserted strategically within the cover text, one after each word.
This way, the secret message is hidden in plain sight, invisible to the naked eye, but retrievable with the right decoding method.

# Audio Steganography ( Hiding TEXT in AUDIO )
1)Convert and Check: Each chunk of audio data (frame) is transformed into an 8-bit format. We then peek at the 4th least significant bit (LSB) of this byte and compare it to the current bit from the secret message.
2)Matching the Message: If the 4th LSB matches the secret message bit, we don't need any changes. However, if they don't match...
3)Modification Magic: We use a bitwise AND operation with a specific number (253) to ensure the 2nd LSB becomes 0. Then, a combination of AND and OR operations sets the 2nd LSB to 1 and prepares the space for the secret bit.
4)Embedding the Secret: Finally, another AND operation with a different number (254) isolates the LSB of the audio data. We then use a bitwise OR to merge this isolated LSB with the next bit (0 or 1) from the secret message, effectively replacing the original LSB with the secret bit.

# Video Steganography ( Hiding TEXT in Video )
This video steganography technique combines encryption and hiding to secure your message. Here's the gist:

1)Scrambling the Message: First, your plain text message is scrambled using the RC4 algorithm. This acts like a secret code, making the message unreadable without the key. RC4 works by creating a unique data stream based on a user-provided key.
2)Key Scheduling: Imagine a list with numbers 0 to 255. RC4 shuffles this list based on the key you provide. It's like a secret recipe for mixing up the data.
3)Stream Generation: Then, RC4 generates a random-looking data stream (keystream) as long as your message. This stream is like a mask used later.
4)Masking the Message: Finally, each piece of your scrambled message is combined (using XOR operation) with a corresponding bit from the keystream. This masking hides the original message within seemingly random data.
