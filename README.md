# Ambiguous-AI-Assisted-Text-Codec
Ambiguous Artificial Intelligence Assisted File (De)Compression Technique


It's all in the title. Actually, the below code is only the compression part, which for us is simpler than the decompression part. The code was written using GPT 3.5, and what it does is generate a Huffman Compression Table, but a modified one. How I modified it is, I had it take the least commonly occurring symbols, which have the longest code, erased that code, and assigned it to the same code as the most commonly occurring symbol, which has the shortest code. It numbers the occurrences of each character in each pair as well, which should help a lot with decompression by removing tons of ambiguity. Obviously, it's still pretty ambiguous. How are we going to decompress a document which has had half of the detail in the compressed string removed? How do we know which letters are which? Well, how do you know that one letter isn't an A vs. a Z? It's probably an A, in most cases. And that's where Artificial Intelligence comes to the rescue! We don't really want A and Z to be paired, we want A, or whatever the most commonly occuring character is, to be paired with the character just past halfway down the list of most commonly occuring characters to be paired with it. That way, a fairly long Huffman code that occurs fairly often is cut down to the length of the most common character, which has the shortest code. And that's harder to decompress, because it isn't as clear which characters are which. However, the compressed string will be even shorter. Using a tool like Tensor Flow, we can compress many text documents, and train a new AI by having it match both the compressed and uncompressed documents. With a large enough data set, it should be enough for a deployment of an AI with access to the API generated by the training data to decompress (actually to an extent, decrypt) the ambiguous document. In this way, we should have a proof of concept for more efficient codecs. 
