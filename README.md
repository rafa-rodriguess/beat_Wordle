
# WORDLE Breaker

## Goal and Motivation

If you live in this world and accessed the internet in the last month, good chances you know what wordle is. But in case you just came back from Pluto, let me in one sentence explain what wordle is:

Wordle is a mind-addictive online game, created by a software engineer called Josh Wardle. Players attempt to guess a five-letter word in six attempts; feedback, in the form of colored tiles, is given for each guess, informing players which letters are in the correct position and which are in other positions of the answer word

For the time being, wordle is only in English and give 1 word per day (thank god).

But let wordle explain itself:

![wordle instructions](wordle%20instructions.png)

You can access wordle in: https://www.powerlanguage.co.uk/wordle/

More about wordle: https://en.wikipedia.org/wiki/Wordle

I was introduced to wordle in the **Eastern University Data Science Master** course Discord channel, by one of our fellow students (tks @Dustin). 

I am from Brazil, and despite my day after day effort, I still have a vocabulary of a 10 years old boy (ok.. even less). Most of it was acquired by watching 80/90 Seinfeld, Friends, and others.

As you can imagine, I got really frustrated after trying to beat the game. So, I came up with an idea to mix what I've learned so far at the masters to "break" the game.

## The Code

It is a python notebook (why not, right?) with a few elements that I describe below:

### The Dictionary

It uses what I call a "dictionary" to suggest a word, from the "Wikipedia Word Frequency" located at https://github.com/IlyaSemenov/wikipedia-word-frequency.
It was created from a wikipedia article dumps from https://dumps.wikimedia.org/enwiki/ and gathered the word frequency distribution data.

### Regular Expression

From that, the code uses a series of [regular expressions](https://simple.wikipedia.org/wiki/Regular_expression#:~:text=A%20regular%20expression%20%28abbreviated%20regexp,of%20characters%20using%20syntactic%20rules.&text=A%20regular%20expression%20processor%20is,that%20examines%20a%20text%20string.) to filter the dictionary after each attempt. 

In every interaction, the code shows which regex was used to filter the dictionary down and the size of the remaining dictionary. The idea is to feed the code back with the game output with 'g' for green, 'y' for yellow, or 'b' for black. I also created an 'x' - used when a word is not recognized.


### Main Function
The main function is:

    break_wordle(attempts, word_length, dictionary, random_word_mode = False)

 - **attempts:** Number of attempts allowed. The code is prepared to deal
   with any number of attempts.
 - **word_length:** Word Length. The code is prepared to deal with any word
   Lengh  
 - **dictionary:** Dictionary to be used
 - **random_word_mode:** If set to `True`, take a guess from the 5% most
   used words. If `False`, take the most used one.


![game played](all%20attempts.png)

