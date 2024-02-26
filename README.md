WARNING: I AM NOT RESPONSIBLE FOR YOUR LOST DATA, OR MISUSE OF AI. KEEP BACKUPS OF ANY FILES YOU USE THIS '3/4-MIRROR-CIPHER' ON. THIS IS A PRE-BETA PROGRAM AND ANY DATA YOU CODE THIS WAY IS VERY LIKELY TO BE CORRUPTED AND LOST FOREVER, OPTIMIZATIONS HAVE NOT BEEN MADE, AND IT IS NOT YET A DEPENDABLE PRODUCT. YOU HAVE BEEN WARNED.

#Update: Decoder Model is starting to take shape. I'm probably going to use a pre-trained model like T-5 and develop several layers on top of that to start with. I also for the first time ran the encoder on a data twice, and handed that to GPT and Gemini to see what they would do make of it. While they do well with data that has only been obfuscated once, they seem very confused with the task when it is layered on top of itself. So confused, in fact, that GPT got stuck in an infinite loop. With some particular training they will probably understand how to approach the task a lot better. I wish I had a finished decoder, it's exciting and fun to watch AI successfully read data that looks like gibberish. However, I've been really, really tired lately, and not feeling well at all. I think I'll take some time to enjoy other endeavors. 

#Update: Encoder4.2 is out now. This one adjusts the format of the key data, which seems to help the AI do a bit better like it used to.

#Update: Added 'Vowels' program. This program will ask you to open a file, and when you give it a text document it will remove all of the vowels and print them as a string in terminal. It seems AI is still able to read these texts, which is interesting. I can't. Without training AI on the 'Encoder4.1' technique, it doesn't seem that it will reliably decode the precoded document anymore. This seemed to take effect with the recent update to Google's AI, Bard, being rebranded as Gemini. I'm not sure on what level these AI's are interacting but it wasn't to this techniques advantage.

#Update: Encoder4.1 now the most recent file. Added a handy gadget that lets you choose a file when you run the program (python3 required). At first, I could get AI's to decode from the pre-coded string quite well, but now it seem's that some artifact in the GPT-a-verse is preventing them from employing basic logic. It's not a problem with the code of the keys, because it's not very heavy encoding and it was working before. So, maybe as we get the numbers problem sorted out and start training models we can fix that little glitch. 

#Update: You will need to tinker with the 'Encoder4.py' file to get a print() of the '3/4-mirror-cipher' text document. This is the (modified_data) after the "#Modify the Data" comment in the code (I think.) Replace 'AskPython2.py' with your test document, making sure it's in the same directory as 'Encoder4.py.' Once you get the altered file, you should see a mish-mash that is more or less readable. You will find that when you compress this document, it is quite a bit smaller than a compressed version of the unaltered document. The native compression of the program still isn't working correctly so you will have to just save both files to txt and then compress them with the format of your choice. This will be more similar to the final implementation anyway, as the concept should be applicable to literally any type of data with the right optimizations. 

To get your data back, well we're in the dark ages of that I'm afraid. Extract your document, which remember you ran it through my cipher program so it's going to come out looking like it had a rough night. Now paste the Key of Original Characters, which should print when you run the program normally, along with the Header of Huffman Codes {} in your favorite AI. Copy and paste the ciphered text as well. You're going to have to figure out how to get to that, for now. It will probably make a kawai comment and then it will very accurately fix the scrambled text. Well, with one hickup. In my experience, AI has a problem with numbers. So you will probably get readable text back along with scrambled numbers. See WARNING at the top of the README.

I can think of a few easy solutions for this:

 1) Assign letters to the number of a 'modified_character,' but not the other way around. Maintaining integrity of the numbers is obviously important. 

 2) If a number collapses into a high letter, replace the letter with the number. This maintains the numbers positions in the document.
 
 3) Numbers have to take precedence to other data types, until a specific API has been trained. And under no circumstances should you pair a number with      another number. Unless:
    
 5) We can create a space efficient number key which uses categorization clues to help the AI. For example: The order the numbers appear in is a prime        number beginning in an odd number, or with an odd number in the middle, or combination of even and odd, etc.
    Is the least common multiple of x and y but not z and y.
    Is concatenation of the operands that result in a certain super-prime number, etc. Ai can make very efficient use of general clues, which you'll see      if you test the pre-codec out. 
 `  


# Ambiguous-AI-Assisted-Text-Codec
Precompression Algorithm that makes your Compression more Compressive


It's all in the title. Actually, the below code is only the compression part, which for us is simpler than the decompression part. The code was written using GPT 3.5, and what it does is generate a Huffman Compression Table, but a modified one. How I modified it is, I had it take the least commonly occurring symbols, which have the longest code, erased that code, and assigned it to the same code as the most commonly occurring symbol, which has the shortest code. It numbers the occurrences of each character in each pair as well, which should help a lot with decompression by removing tons of ambiguity. Obviously, it's still pretty ambiguous. How are we going to decompress a document which has had half of the detail in the compressed string removed? How do we know which letters are which? Well, how do you know that one letter isn't an A vs. a Z? It's probably an A, in most cases. And that's where Artificial Intelligence comes to the rescue! We don't really want A and Z to be paired, we want A, or whatever the most commonly occuring character is, to be paired with *the next most commonly occuring character.* This makes the list of codes half the length, and the resulting codes can be shorter. And that's harder to decompress, because it isn't as clear which characters are which. However, the compressed string will be even shorter (I think, I need debugged programs in order to crunch the numbers on which pairings make the shortest strings). You can take messages coded this way and play a modified 'cross-word puzzle' game with them, decoding the messages like it's a game (Game B is quite a bit harder than game A, that much is certain). After we can compress many text documents with an unbugged code, we can use a tool like Tensor Flow to train an AI by having it match both the compressed and uncompressed documents. With a large enough data set, it should be enough for a deployment of an AI with access to the API generated by the training data to decompress (actually to an extent, decrypt) the ambiguous document. In this way, we should have a proof of concept for slightly more effecient codecs when enough hardware resources are present. 

The main problem I'm currently having is that the module that deals with the Huffman compression technique doesn't really want to work in a different way, so that even if the chart is generated correctly, it writes compressed strings which aren't right. 

Additionally, the chart seems to be working backwards, such that the most common character is getting the longest code, which isn't right at all. As it runs now, in a typical sample text space will be the most commonly occuring character, co-occuring with the least commonly occuring character. The script is assigning the long binary code to the frequent character, which (hilariously) makes our compressed string much longer than intended. We would have to write that out by hand though, because currently the output string is a mess of confused codes which often do not even exist in the table.

With very, very powerful computers, such as quantum computers, you could even 'fold' the data like this until every available character belongs to either the binary codes 1 or 0. Only one of two possible options. Well, it's not resource intensive to code the data this way, but to decode it is another matter entirely. It takes an AI with the ability to see many moves ahead, draw many pictures at once, and delineate between the contexually likely possibilities in order to decompress these strings at all. As it stands, I think halving the data sample only 1 time is very reasonable for current hardware to work with. 

#Update: I don't think the Huffman trees are being built as pairs, but instead items are being paired after the tree is generated, and then the binary codes are being mashed together in some strange way which is misleading to someone without experience in these things. It seems that we'll have to modify the underlying code. More on that later, unless someone wants to do it for me :)

#Update: It appears as though a solution is to list the items by frequency, define the pairs (which will vary in the final implementation), list the desired pairs as such, extract the sum of the occurences of the pairs, and then heap the pairs again based on their sum. This should build the desired tree and give us the basis for the rest of our compressor. I'm not sure if heapq supports working with pairs like this, but I'm sure we will find out if we dig around a bit more. [This turned out to be the wrong approach, btw]



#Update: Got the encoder working to a respectable degree, at least at first glance. I think it's working, but I haven't tested it yet. I've been down several rabbit holes in this coding adventure, all the way down to the drains of closed flip flops. I'm dizzy, honestly, from being 'gated' in circles, and somehow I wound up in the Shapley Cluster being repelled by the Dipole Repeller, shadey coding and all. WELL. LOOKS LIKE I BETTER BE HITTIN' THE DUSTY TRAIL. Actually let's backtrack a minute. Now that we know how to cram a modified string into an algorithm, we can test the machine and see if it's possible to write our training documents. If it is, it's off to the races, which is to say, for me, tensor flow and the curse of limited computational power. Well, you can't have everything in life. If anyone finds this message floating in a tomato soup can somewhere near Alpha Centari, write it in a book somewhere, and don't tell them that I'm out of coffee or that the dryer is broken.

#Update: Ok it's still broken, but much less than before.

#Update: Pretty sure it works now. I need to go outside for a while.

#Update: Harry Potter and the Code of Ambiguity. Once upon a time in a faraway land... Ok nearby, actually. But it looks like an old abandoned warehouse when muggles look at it. Unless they have love in their heart, or something. In which case it looks like a flying Ford Anglica - wait a minute, why didn't they just enchant the flying Ford Anglica to look like an ordinary flying object, such as a UFO? Anyway. The code now prints something that would be helpful for assembling training data. More in the pipeline.
