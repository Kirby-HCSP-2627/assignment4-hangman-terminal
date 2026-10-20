# Assignment #4 Hangman Terminal Game

### Intro
We are going to be making a hangman game. 

### Relevant Info 
In general, when taking user input there are a few things we want to check: <br/>
1. Check the user input is what you want
2. Clean up the user input, remove extra blank spaces and convert to all lowercase
These might be some useful methods/functions. Google them to find the documentation
```python
isalpha()
string.strip()
```
We are also going to be using the built-in libraries string and random to help us with the game.
```python
list_of_words = ["hello", "bye", "goodnight"]
random.choice(list_of_words) # returns an object chosen randomly from a list
```
### The Program
You will implement a variation of the classic word game Hangman. If you are unfamiliar with the rules of the game, [read here](http://en.wikipedia.org/wiki/Hangman_(game)) . Don’t be intimidated by this problem it's actually easier than it looks! I have broken down the whole game into smaller parts. I would recommend to bring up the google slides for some more examples. The following parts are each section in the program with your tasks. 

#### Game Architecture
1. The computer must select a word at random from the list of available words that was provided in words.txt. Write a function get_word() that takes a string, filename, and returns a random word read from the file. The file, word_list.txt, has all the words on 1 line separated by commas. 

2. Users start with 6 guesses.

3. At the start of the game, let the user know how many letters the computer's word contains and how many guesses they start with.

4. The computer keeps track of all the letters the user has not guessed so far and before each turn shows the user the “remaining letters”

#### User Computer Interaction
The game flows as follows:
1. Before each guess, you should display to the user:
    1. A reminder of how many guesses they have left after each guess.
    2. All the letters the user has not yet guessed
2. Ask the user to supply one guess at a time. (More details in next slide)
3. After each guess:
    1. The user should be told whether the letter is in the computer’s word.
    2. Display to the user the computer’s word, with guessed letters displayed and unguessed letters replaced with an underscore and space “_ ”
4. At the end of the guess, print some dashes “---” to help separate individual guesses from each other

#### User Input Requirements
1. You may assume that the user will only guess one character at a time, but the user can choose any number, symbol, or letter. Your code should accept capital and lowercase letters as valid guesses!
2. If the user inputs anything besides an alphabet (symbols, numbers), tell the user that they can only input an alphabet character. 
    1. Because the user might do this by accident, they should get 3 warnings at the beginning of the game
    2. Each time they enter an invalid input, or a letter they have already guessed, they should lose a warning
    3. If the user has no warnings left and enters an invalid input, they should lose a guess

#### Game Rules
1. The user starts with 3 warnings.
2. If the user inputs anything besides an alphabet character, tell the user that they can only input an alphabet character.
    1. If the user has one or more warnings left, the user should lose one warning. Tell the user the number of remaining warnings.
    2. If the user has no remaining warnings, they should lose one guess.
3. If the user inputs a letter that has already been guessed, print a message telling the user the letter has already been guessed before.
    1. If the user has one or more warnings left, the user should lose one warning. Tell the user the number of remaining warnings.
    2. If the user has no warnings, they should lose one guess.
4. If the user inputs a letter that hasn’t been guessed before and the letter is in the secret word, the user loses no guesses.
5. Consonants: If the user inputs a consonant that hasn’t been guessed and the consonant is not in the secret word, the user loses one guess if it’s a consonant.
6. Vowels: If the vowel hasn’t been guessed and the vowel is not in the secret word, the user loses two guesses. Vowels are (a, e, i , o, u). y does not count as a vowel.

#### Game Rules
1. The game should end when the user constructs the full word or runs out of guesses
2. If the player runs out of guesses before completing the word:
    1. Tell them they lost
    2. Reveal the word to the user
3. If the user wins:
    1. Print a congratulatory message
    2. Tell the user their score
<div align="center">
  Total Score = guesses_remaining * number of unique letters in secret_word
</div>

### Example Output
[Click this link to find an example of a win and a loss.](https://docs.google.com/document/d/1k9NZkxN-MRVW56ojP6_6vZ76ZwAXk83YSgDLNPAw_Aw/edit?usp=sharing)

### Submitting 
To submit your project:<br/>
1. Open a terminal window in vscode in your project folder
2. Replace file_name with the name of the file you edited
```bash
git add file_name.py
```
3. Type short summary of what you added in between quotations
```bash
git commit -m "your message here"
```
4. Push it to your repository
```bash
git push
```
5. Confirm on your GitHub account, might take ~1 or 2 minutes to update on GitHub website
