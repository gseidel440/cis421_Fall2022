# CIS421 Project 1
## Contributors
Garrett Seidel,
Tehron Phillips
## General Skills Solutions
**1. Wave a Flag (10 Points, Tehron)**

In the first practice exercise we had to wave a flag. We had to use the copy and paste the link into my terminal. We then use the wget function in order to get the link into my terminal. We think had to make it executable in order for me to run the information in the link. After that we still couldn't find the flag so we used the -h function and found the flag in there.

**2. Obedient Cat (5 Points, Garrett)**

First I copied the link. I then opened it in the webshell and the answer for the flag was the only thing that was in the file, which then I entered it in and it was correct.

**3. Nice Netcat (15 Points, Garrett)**

I ran the command “nc mercury.picoctf.net 43239”. This returned a list of ASCII numbers that I needed to convert into text. I used this website, duplichecker.com, and was able to get the answer.

**4. Static Ain't Always Noise (20 Points, Garrett)**

I imported both the static file and the bash script. I bashed the script and it gave me a .txt file. I opened the file and within the text the answer was there.

**5. Tab, Tab, Attack (20 Points, Tehron)**

In the second practice exercise we had to unzip a file with the unzip command. After unzipping the file we read the hint which told me to complete tab. We at first had an issue with it but once we took the file and looked inside of it by using the ls command. This opened up another file that we then used the cd command to look inside of that file. We then repeated this process until we got to the file fang-of-haynekhtnamet. We got stuck here so we did some research and learned to use the strings command ($ strings fang-of-haynekhtnamet), in order to find out what was inside of the file and found the flag. (https://medium.com/@arthDetroja/picoctf-write-up-tab-tab-attack-5e2ba52e25a4)

**6. Magikarp Ground Mission (30 Points, Garrett)**

For this one, I pressed “launch instance” and it gave me a connection. I then used ssh to connect to it. By doing ls, it gave me the first part of the answer and instructions for the second part. I went through the directories and found the second and third part of the answer. I combined them all and it gave me the correct answer.

**7. Let's Warm Up (50 Points, Garrett)**

Since it was a hexadecimal, I used the echo command and did echo -e “\x70” and it printed out the letter p which was the answer.

**8. Warmed up (50 Points, Garrett)**
For this one, it asks "What is 0x3D (base 16) in decimal (base 10)?" We did not know what the conversion was for this, so we used an online converter, and it came back with the answer 61, which was the flag answer.

**9. 2Warm (50 Points, Garrett)**

In the third practice exercise we had to convert the number 42(base10) to binary (base2). In order for us to find it out we used a converter. We then typed in the answer into picoCTF and got the answer correct.

**10. Plumbing (200 Points, Tehron and Garrett)**

First, I tried to ssh to the link to connect to it, but there was no password so that didn’t work. I then tried to netcat the link, and this worked, but it printed too many lines of text to find the answer. I did grep pico and it found the answer and printed it.

## Web Exploitation Solutions
**1. GET aHEAD (20 Points, Tehron)**

First I copied the link and used wget to get the link and then I used strings to open the file up. I saw the html code for the program and the two choices I thought I was given were GET and POST. I then got confused and started to do some research. I then found that the header ‘HEAD was the other choice although I had no way to get the code in order to get the flag. I then found out to use the curl -I HEAD -i command in order to find the flag (CTFtime.org / picoCTF 2021 / Get aHEAD / Writeup)

**2. Where are the Robots (100 Points, Garrett)**

Opening the problem, they give you a link to a website that says welcome and where are the robots on it. There is nothing else on the page and when viewing the page source code, it doesn't show you much from it other than the basic code. There are text files that disallow certain parts of an html to run sometimes. They hint that the creator doesn't want you to look at one certain part, or the html. The title also hints that the robots are the hidden part, so if you add robots.txt to the end of the html, it shows the disallowed part of the html. By doing this, it showed us the end of the link, and we added it to the html, and we "found the robots" or the flag.

## Cryptography Solutions
**1. Mod 26 (10 Points, Tehron)**

The problem was just the flag was encypted. Instead of doing this by hand and spending hours and hours, I used a website (https://www.dcode.fr/caesar-cipher) and used ROT13 as the decoder and it was able to decode the cipher and give the answer for the flag.

**2. 13 (100 Points, Garrett)**

For this one, it was similar to the Mod 26 problem, where the flag was encrypted. They gave the hint in the problem about ROT13, which is a decoder language. We took the encrypted flag and put it into the ROT13 decoder and we got the answer for the flag from it.

## Reverse Engineering Solutions
**1. Transformation (20 Points, Tehron)**

We tried to find the flag from what was given to begin the practice '.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)]). Although with the lack of getting the right python code for the flag we were not able to complete it.

**2. File-run-1 (100 Points, Tehron)**

We downloaded the file given to me and was told to run the file. We ran the file with ./run and the flag popped up right after We had ran it.

## Forensics Solutions
**1. Information (10 Points, Tehron and Garrett)**

The problem gave us a .jpg as we were to inspect it to find the flag. When we opened it there was no flag visible anywhere. We then decided to look at the metadata of the .jpg using the exiftool command. By using the command, we could see that the license looked like it was encoded. I look up an encoded online and pasted the string and it gave us the answer for the flag.

**2. Lookey Here (100 Points, Garrett and Tehron)**

For this one, they gave you a text file of a book. The hint says to search the text by knowing the prefix, or pico. We opened the text file and did CTRL+F and searched for the prefix “pico” and it brought us to the flag’s answer.

## Binary Eploitation Solutions 
**1. Stonks (20 Points Garrett)**

For this problem, we are given a connection to netcat to and the code for it. This one gave us some trouble. We looked into the code and noticed that the “stonks” that were returned to us when inputting the API token were based on what we entered, so we tried to use a %p specifier to see if it would return a series of hex values. This ended up working, but due to the lack of knowledge with hex numbers, we could not figure out how to decode this and find out the flag answer from the decoded hex numbers.

**2. RPS (200 Points, Garrett)**

For this problem, it gave us the code to play rock paper scissors against the computer or code that was written. The hint says “How does the computer know if you won?”. We looked at the code and it all seemed self explanatory, so we played the game. Statistically thinking, in order to beat the computer 5 times in a row and get the flag would take hours, so we wondered what would happen if we tried to outthink or “break” the code. Instead of playing just one answer, we typed “rockpaperscissors” and this bypassed as an answer and was able to beat the computer, since the correct answer was still within what we wrote. We answered with this 5 times and was able to beat the computer and was awarded with the answer for the flag.

<span style="color: red;"> **Highest Difficulty (500 Points, Tehron and Garrett)**<span>


We started off by implementing the links that were given to me in the beginning. We then used the strings command on the site to get the site up and look at the code to search around. After not finding anything in the site link, We then looked at the bundle link. After looking at that We got confused as to where to go from there. THere were many files and trying to look through the and look at the data and code, we couldn't make out how to be able to draw the flag from the files. From it seem like, by writing a scipt of somesort to ruun, this may be able to draw out some of the flaws behind the code and then utilize what it gave us to then get the answer for the flag.