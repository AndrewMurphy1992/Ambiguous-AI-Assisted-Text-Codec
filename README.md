WARNING: I AM NOT RESPONSIBLE FOR YOUR LOST DATA. KEEP BACKUPS OF ANY FILES YOU USE THIS '3/4-MIRROR-CIPHER' ON. THIS IS A PRE-BETA PROGRAM AND ANY DATA YOU CODE THIS WAY IS VERY LIKELY TO BE CORRUPTED AND LOST FOREVER, OPTIMIZATIONS HAVE NOT BEEN MADE, AND IT IS NOT YET A DEPENDABLE PRODUCT. YOU HAVE BEEN WARNED.


#Update: You will need to tinker with the 'Encoder4.py' file to get a print() of the '3/4-mirror-cipher' text document. This is the (Data) before the "#Modify the Data" comment in the code. Replace 'AskPython2.py' with your test document, making sure it's in the same directory asy 'Encoder4.py.' Once you get the altered file, you should see a mish-mash that is more or less readable. You will find that when you compress this document, it is quite a bit smaller than a compressed version of the unaltered document. The native compression of the program still isn't working correctly so you will have to just save both files to txt and then compress them with the format of your choice. This will be more similar to the final implementation anyway, as the concept should be applicable to literally any type of data with the right optimizations. 

To get your data back, well we're in the dark ages of that I'm afraid. Extract your document, which remember you ran it through my cipher program so it's going to come out looking like it had a bad day at work. Now paste the Key of Original Characters, which should print when you run the program normally, along with the Header of Huffman Codes {} in your favorite AI. Copy and paste the ciphered text as well. You're going to have to figure out how to get to that, for now. It will probably make a kawai comment and then it will very accurately fix the scrambled text. Well, with one hickup. In my experience, AI has a problem with numbers. So you will probably get readable text back along with scrambled numbers. See WARNING at the top of the README.

I can think of a few easy solutions for this:

 1) Assign letters to the number of a 'modified_character,' but not the other way around. Maintaining integrity of the numbers is obviously important. 

 2) If a number collapses into a high letter, replace the letter with the number. This maintains the numbers positions in the document. 

 3) Alternatively, we may be able to use a prime number expression to store value of the numbers in order.



# Ambiguous-AI-Assisted-Text-Codec
Ambiguous Artificial Intelligence Assisted File (De)Compression Technique


It's all in the title. Actually, the below code is only the compression part, which for us is simpler than the decompression part. The code was written using GPT 3.5, and what it does is generate a Huffman Compression Table, but a modified one. How I modified it is, I had it take the least commonly occurring symbols, which have the longest code, erased that code, and assigned it to the same code as the most commonly occurring symbol, which has the shortest code. It numbers the occurrences of each character in each pair as well, which should help a lot with decompression by removing tons of ambiguity. Obviously, it's still pretty ambiguous. How are we going to decompress a document which has had half of the detail in the compressed string removed? How do we know which letters are which? Well, how do you know that one letter isn't an A vs. a Z? It's probably an A, in most cases. And that's where Artificial Intelligence comes to the rescue! We don't really want A and Z to be paired, we want A, or whatever the most commonly occuring character is, to be paired with *the next most commonly occuring character.* This makes the list of codes half the length, and the resulting codes can be shorter. And that's harder to decompress, because it isn't as clear which characters are which. However, the compressed string will be even shorter (I think, I need debugged programs in order to crunch the numbers on which pairings make the shortest strings). You can take messages coded this way and play a modified game of 'hangman' with them, decoding the messages like it's a game (Game B is quite a bit harder than game A, that much is certain). After we can compress many text documents with an unbugged code, we can use a tool like Tensor Flow to train an AI by having it match both the compressed and uncompressed documents. With a large enough data set, it should be enough for a deployment of an AI with access to the API generated by the training data to decompress (actually to an extent, decrypt) the ambiguous document. In this way, we should have a proof of concept for slightly more effecient codecs when enough hardware resources are present. 

The main problem I'm currently having is that the module that deals with the Huffman compression technique doesn't really want to work in a different way, so that even if the chart is generated correctly, it writes compressed strings which aren't right. 

Additionally, the chart seems to be working backwards, such that the most common character is getting the longest code, which isn't right at all. As it runs now, in a typical sample text space will be the most commonly occuring character, co-occuring with the least commonly occuring character. The script is assigning the long binary code to the frequent character, which (hilariously) makes our compressed string much longer than intended. We would have to write that out by hand though, because currently the output string is a mess of confused codes which often do not even exist in the table.

With very, very powerful computers, such as quantum computers, you could even 'fold' the data like this until every available character belongs to either the binary codes 1 or 0. Only one of two possible options. Well, it's not resource intensive to code the data this way, but to decode it is another matter entirely. It takes an AI with the ability to see many moves ahead, draw many pictures at once, and delineate between the contexually likely possibilities in order to decompress these strings at all. As it stands, I think halving the data sample only 1 time is very reasonable for current hardware to work with. 

#Update: I don't think the Huffman trees are being built as pairs, but instead items are being paired after the tree is generated, and then the binary codes are being mashed together in some strange way which is misleading to someone without experience in these things. It seems that we'll have to modify the underlying code. More on that later, unless someone wants to do it for me :)

#Update: It appears as though a solution is to list the items by frequency, define the pairs (which will vary in the final implementation), list the desired pairs as such, extract the sum of the occurences of the pairs, and then heap the pairs again based on their sum. This should build the desired tree and give us the basis for the rest of our compressor. I'm not sure if heapq supports working with pairs like this, but I'm sure we will find out if we dig around a bit more. [This turned out to be the wrong approach, btw]



#Update: Got the encoder working to a respectable degree, at least at first glance. I think it's working, but I haven't tested it yet. I've been down several rabbit holes in this coding adventure, all the way down to the drains of closed flip flops. I'm dizzy, honestly, from being 'gated' in circles, and somehow I wound up in the Shapley Cluster being repelled by the Dipole Repeller, shadey coding and all. WELL. LOOKS LIKE I BETTER BE HITTIN' THE DUSTY TRAIL. Actually let's backtrack a minute. Now that we know how to cram a modified string into an algorithm, we can test the machine and see if it's possible to write our training documents. If it is, it's off to the races, which is to say, for me, tensor flow and the curse of limited computational power. Well, you can't have everything in life. If anyone finds this message floating in a tomato soup can somewhere near Alpha Centari, write it in a book somewhere, and don't tell them that I'm out of coffee or that the dryer is broken.

#Update: Ok it's still broken, but much less than before.

#Update: Pretty sure it works now. I need to go outside for a while.

#Update: Harry Potter and the Code of Ambiguity. Once upon a time in a faraway land... Ok nearby, actually. But it looks like an old abandoned warehouse when muggles look at it. Unless they have love in their heart, or something. In which case it looks like a flying Ford Anglica - wait a minute, why didn't they just enchant the flying Ford Anglica to look like an ordinary flying object, such as a UFO? Anyway. The code now prints something that would be helpful for assembling training data. More in the pipeline.
