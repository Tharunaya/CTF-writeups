# Forwards from Grandma - 100 points
##### Message
My grandma sent me this email, but it looks like there's a hidden message in it. Can you help me figure it out?
##### Content
[Mail](tmp.eml)
##### Solution
By having a closer look at the subject of the mail, one could see a large amount of FWD: and RE:'s - which is not too unusual in a mail from grandma, but the swirly brackets in between caught my attention as it resembled the flag format. 
My initial guess was it being binary with the FWD: as a 0 or 1 and the RE: as a 1 or 0, respectively, but as that lead to nothing I figured it was morse code instead. Knowing that the morse code before the opening of the swirly brackets had to be "flag", I could confirm my hypothesis and find out the correct mapping.
```sh
"FWD:"  => "."
"RE:"   => "-"
```
The resulting morse code was: “..-..-...---.{....--.---..........--.-.----.-..}”
The difficulty here was that no spaces were in between the morse code letters, meaning that there were a ton of possible solutions (like 1628277960) for the text between the curly brackets due to the ambiguity (e.g. "..." can mean eee, ie, ei or s).

After some while and running a function that would return me every possible combination of spaces inserted for more than six hours (Spoiler Alert: it didn't finish), I noticed that words in the flags were usually seperated by underscores. The morse code for underscores is quite recognizable (..--.-) and occured two times in the encoded flag. With that information, I could now split my flag into three seperate words of much shorter length and thus less ambiguities.
```
“flag{.._--........_.----.-..}”
```
With the initial function for inserting spaces in combination with a function for decoding the morse code, I could now determine all possible solutions for my three words. As I thought the words would either be in a dictionary or be leetspeak and thus containing numbers, I implemented optional checks for both possibilities. (1)
By picking the most plausible words from the resulting list, I ended up with the right flag.
```
flag{i_miss_aol}
```
(1) That would have probably worked great, but when transcribing the FWD:'s and RE:'s to morse I had noted down one dot too much which lead to no sensical dictionary entries. 
##### Resources
Function for inserting spaces: https://www.geeksforgeeks.org/print-possible-strings-can-made-placing-spaces/
Function for decrypting the morse code: https://www.geeksforgeeks.org/morse-code-translator-python/