# Ambiguous-AI-Assisted-Text-Codec
Ambiguous Artificial Intelligence Assisted File (De)Compression Technique


It's all in the title. Actually, the below code is only the compression part, which for us is simpler than the decompression part. The code was written using GPT 3.5, and what it does is generate a Huffman Compression Table, but a modified one. How I modified it is, I had it take the least commonly occurring symbols, which have the longest code, erased that code, and assigned it to the same code as the most commonly occurring symbol, which has the shortest code. It numbers the occurrences of each character in each pair as well, which should help a lot with decompression by removing tons of ambiguity. Obviously, it's still pretty ambiguous. How are we going to decompress a document which has had half of the detail in the compressed string removed? How do we know which letters are which? Well, how do you know that one letter isn't an A vs. a Z? It's probably an A, in most cases. And that's where Artificial Intelligence comes to the rescue! We don't really want A and Z to be paired, we want A, or whatever the most commonly occuring character is, to be paired with *the next most commonly occuring character.* This makes the list of codes half the length, and the resulting codes can be shorter. And that's harder to decompress, because it isn't as clear which characters are which. However, the compressed string will be even shorter. You can take messages coded this way and play a modified game of 'hangman' with them, decoding the messages like it's a game. After we can compress many text documents with an unbugged code, we can use a tool like Tensor Flow to train an AI by having it match both the compressed and uncompressed documents. With a large enough data set, it should be enough for a deployment of an AI with access to the API generated by the training data to decompress (actually to an extent, decrypt) the ambiguous document. In this way, we should have a proof of concept for more efficient codecs. 

The main problem I'm currently having is that the module that deals with the Huffman compression technique doesn't really want to work in a different way, so that even if the chart is generated correctly, it writes compressed strings which aren't right. 

Additionally, the chart seems to be working backwards, such that the most common character is getting the longest code, which isn't right at all. As it runs now, in a typical sample text space will be the most commonly occuring character, co-occuring with the least commonly occuring character. The script is assigning the long binary code to the frequent character, which (hilariously) makes our compressed string much longer than intended. We would have to write that out by hand though, because currently the output string is a mess of confused codes which often do not even exist in the table.
