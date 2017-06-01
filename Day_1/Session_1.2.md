# Day 1, Session 2
### 11:00 am – 12:00 pm
## Command-line introduction
#### (11:00–11:30)

### Getting started

In Jupyter, click `New`, then `Terminal` in the upper right to launch a new terminal window. Before we go further, you may find it helpful to open the following cheat sheet in your browser: Unix/Linux Command Reference ()(http://cc.iiti.ac.in/lcommands.pdf).

First, a few notes on semantics. While in many cases we can use the terms “command line,” “terminal,” and “shell” interchangeably, each has a different technical denotation.

“**Command line**” has the broadest scope, referring to a style of interface. A command-line interface (CLI), also known as a command-line interpreter, is any system in which all interaction occurs via text-based commands issued through a keyboard.

A **terminal**, or more accurately a terminal emulator, is an application in your local operating system that essentially just provides a window to type in. We're using Jupyter's terminal through the browser so that everyone in the class is on the same page. Most macOS users use [Terminal](https://en.wikipedia.org/wiki/Terminal_(macOS)), while [Cygwin](https://www.cygwin.com/) is a popular option for Windows users who prefer a Unix-style interface to the DOS command prompt. In most versions of Linux, pressing `Ctrl+Alt+T` will launch a new terminal window.

In your terminal window, type the following and press return. (Note that there is a space after `echo`.)

```
echo $SHELL
```

A **shell** is the software layer between user input and the rote world of file system maintenance. A graphical user interface (GUI) like macOS or Windows is technically considered a shell, but if someone refers to “the shell” they typically mean a command-line interpreter such as [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)). 

The command you entered above returns `/bin/bash`, which is the location of Bash’s “binary,” or machine-readable application file.

### The file system

Unix-like operating systems are based on a metaphor: a nested set of directories and data files, forming a tree structure that begins at the root directory `/`. A benefit of this arrangement is that each file can be uniquely identified using a pathname of the following format:`/directory1/directory2/directory3/file.txt`. Our Docker container is running Ubuntu Linux, which has a separate file system from the primary operating system you're using (macOS, Windows, GUI-based Linux, etc.). The exception is `sharedfolder`, which is a shared volume between the two operating systems.

In a shell session, at any given moment a user metaphorically occupies a particular "working directory" within this greater tree structure. Enter the `pwd` ("print working directory") command to see your current location.

```
pwd
```

For convenience, our Docker container always starts us off in `/home/sharedfolder` by default.

The root directory, `/`, is just like any other folder in the system. Enter the following to change your working directory to root.

```
cd /
```

You won't get any obvious feedback, but you'll notice the location indicted to the left of your cursor has changed. You can view the contents of the current directory with the `ls` command.

```
ls
```

![](img/cli01.png)

You should see a list of directories including "bin," "boot," "dev", and so on. Add the `-l` option and you’ll see more information on each file.

```
ls -l
```

![](img/cli02.png)

You can find dozens of other options in the manual for `ls`, which you can launch like so.

```
man ls
```

Use the arrow keys to scroll, then press `q` to return to the shell. You can launch so-called "man pages" this way for most command-line programs installed on your system.

### Bash interface tips

Now let's return to our shared folder.

```
cd /home/sharedfolder
```

If you haven't already done so, enter the following command to download a set of sample audio files.  

```bash
wget -i http://www.stephenmclaughlin.net/HILT/Day_1/Session_1.1_files.txt
```

Now use `ls` to list the files in the current directory.

We can use `du` (short for "disk usage") to check the size of a file in bytes. Try adding the `-h` option after `du` to get the size in a more human-readable format.

```
du sine_440.wav
```

Tab completion is a useful feature of most Unix-like CLIs. If you type the first few letters of a long filename, pressing tab will automatically fill in the rest (as long as there's only one file in the directory beginning with those letters). Type out the following, then press tab to finish the filename. 

```
du My
```

![](img/cli03.png)

You'll note that every space in the filename is preceded by a backslash; these are called **escaped** spaces. Because Bash uses spaces to indicate boundaries between each element of a command, the backslash makes it clear that the following space is part of the filename.

Press return to run that command. Just for fun, let's see what happens when we don't escape our spaces.

```
du Myles - Philly ICA - 2010 - interstitial.mp3
```

![](img/cli04.png)

The `du` tool looks for a file called `Myles`, then one called `-`, and so on. As an alternative, we can use quotation marks to make it explicit that the filename, including spaces, is a single chunk.

```
du "Myles - Philly ICA - 2010 - interstitial.mp3"
```

To make your life easier, you may want to avoid using spaces in the names of files you create. The underscore (`_`) is a good alternative.

Now enter the same command followed by `&&` and press return.

```
du "Myles - Philly ICA - 2010 - interstitial.mp3" &&
```

![](img/cli05.png)

Nothing happens! You're stuck in command-line limbo, and pressing return repeatedly doesn't help. If this sort of thing happens by mistake, press `Ctrl+c` (i.e., the `Ctrl` or `control` key and the `c` key at the same time).  This will cancel what you've just entered and bring you back to the regular command prompt. (Incidentally, `&&` is used to string together multiple commands, usually in the same line.)

You may wonder why we're spending so much time on these fiddly Bash details in a course on audio machine learning. The reason is that these non-intuitive interface quirks can be *very* frustrating for beginners — and most programming don't mention them, leaving students to figure them out by trial and error.

### ExifTool and manipulating files

[ExifTool](http://owl.phy.queensu.ca/~phil/exiftool/) is a great CLI program for reading and writing metadata for a wide range of media file formats. Enter the following command to view information about the MP3 file we've been working with. Because the output won't all fit in the terminal window, note that you can scroll up to see the rest.

```
exiftool "Myles - Philly ICA - 2010 - interstitial.mp3"
```

![](img/cli06.png)

In Unix-like systems, we can use the the `>` operator to write terminal output to disk. The following command will create a new text file called `Myles_metadata.txt`.

```
exiftool "Myles - Philly ICA - 2010 - interstitial.mp3" > Myles_metadata.txt
```

Note that you don't get any feedback in the terminal. Go to your desktop and open `sharedfolder`, then open the new file in your text editor of choice.

You can also use the `cat` tool to quickly view a file's contents in the terminal.

```
cat Myles_metadata.txt
```

In addition to `cat`, several other useful CLI tools for viewing text files are `head`, `tail`, and `less`. Try them all if you like. When using `less`, you can press `q` to return to the command prompt.

If you use `>` with a filename that already exists, you'll simply overwrite that file. Using `>>` instead will add your new output to the end of the existing file. The following command will run `exiftool` on all files in the current directory and write the output to a single text file.

```
exiftool * >> All_metadata.txt
```

We can also add text to the beginning and/or end of the `*` wildcard operator to filter by filename.

```
exiftool *.wav >> All_WAV_metadata.txt
```

```
exiftool *.mp3 >> All_MP3_metadata.txt
```

Now let's make a new directory and move those text files into it. The following command creates a directory called `Metadata_files`.

```
mkdir Metadata_files
````

We can use the `mv` tool to move a single file into the new directory.

```
mv All_metadata.txt Metadata_files
```

Or we can move every file ending in ".txt" like so. 

```
mv *.txt Metadata_files
```

Now let's `cd` into our new directory and view its contents.

```
cd Metadata_files
ls
```
![](img/cli07.png)

A useful shortcut is `../`, which refers to the parent directory of our current location on the file tree. Let’s use it to `cd` back to `sharedfolder`.

```
cd ../
```

Finally, we’ll delete the directory we just created along with its contents. Entering `rm` followed by a filename will delete that file; adding the `-r` option tells it to remove files recursively, meaning everything in the specified folder gets wiped out.

```
rm -r Metadata_files 
```

Be careful with `rm`, especially in recursive mode. It deletes files permanently rather than sending them to a Trash folder, so a small mistake can really ruin your day.










#### **10.** Programming basics in Python (as much as time permits)
To get started using Python, simply enter `python` in the shell.

python

We’ve just switched from the standard shell to the Python environment, which you can tell at a glance by the ">>>" to the left of your cursor. We’re in what’s known as a language shell or a read-eval-print loop (REPL), in which any commands we enter will be interpreted as Python code. You can leave Python at any time by entering the `quit()` command.

We’ll begin by assigning some data to variables.

x=5
y=5.0
z="Hello"

If you type `x` and hit return, you’ll notice the variable’s current value is output on the line below. Trying the same with `x+2` will return 7.

x+2

> *Output:*
>
> 	7

Note that `x+x` gives a result of 10, while `x+y` returns 10.0. That’s because 5 and 5.0 are different data types in Python. The former is an **int**, or integer, while the latter is a **float**, or floating point value.

Now try using the `+` operator on two strings.
z+" world"

> *Output:*
>
> 	'Hello world'

Note that `+` is used for two entirely different purposes: adding numbers and concatenating strings. When the same symbol performs multiple tasks in different contexts, it’s described as overloaded.

By the way, you can use single or double quotes to enclose string text in Python. We’ll talk more about this next week.

Next we’ll link a series of values using Python’s list data type. There several ways to represent an ordered sequence of items in Python, but we’ll be using list most frequently.

eu*countries='Austria', 'Belgium', 'Bulgaria', 'Croatia', 'Republic of Cyprus', 'Czech Republic', 'Denmark', 'Estonia', 'Finland', 'France', 'Germany', 'Greece', 'Hungary', 'Ireland', 'Italy', 'Latvia', 'Lithuania', 'Luxembourg', 'Malta', 'Netherlands', 'Poland', 'Portugal', 'Romania', 'Slovakia', 'Slovenia', 'Spain', 'Sweden', 'UK' ()

We can now refer to individual list members using bracket annotation.

eu*countries3 ()

The command above returns the string "Croatia," which is located at index 3. As in most programming languages, we begin counting from 0 when working with ordered data.

If you try to access an out-of-range index value you’ll get an error.

eu*countries99 ()

We can also create a subset of a list using Python’s slice notation. The following will return a list containing four items, beginning at index 3 in `eu_countries`.

eu*countries3:7 ()

Leaving one side of the colon blank will include all items on that end of the list.

eu*countries5: ()
eu*countries:10 ()

We can also use negative numbers to count backwards from the end of a list. The following will return "UK," the final string in the list.

eu*countries-1 ()

Under the hood, every string in Python is actually a list of individual characters. In the example below, `word[7]` returns the letter "e," while `word[7:20]` returns "establishment."

word="antidisestablishmentarianism"
word7 ()
word7:20 ()

If we need to know the length of a list or string, the `len` function can tell us.

len(eu*countries)
len(word)

Conditional statements are a fundamental part of all programming languages. We use the `if` operator to evaluate conditionals.

number=12
if number==12:
 print("The value is 12, an integer.")

By adding `else`, we can tell Python to do something if the conditional isn’t true.

number=10
if number==12:
 print("The value is 12, an integer.")
else:
 print("The value is not 12.")

A **for loop** is a structure that lets us iterate through lists and other data structures so we can refer to each item one at a time.

for country in eu*countries:
print(country + ' is great.')

Finally, we can create functions to automate repetitive processes. Use the `def` declaration to start s function definition. The code below will produce the same output as the last example.

```python
def is*great(word):
return word + ' is great.'

for country in eu*countries:
print(is*great(country))
```

In this case we’re not saving much effort, but as we proceed you’ll find that functions will help you write simpler, more readable code.

#### **11.** Accessing the shell from Python with the `os` package (if time permits)
The next section is intended as an instructor demonstration, to be included if time permits.

First, let’s check the length of the film with `exiftool`. Open a new terminal window and enter the following.
cd ~/Desktop
exiftool Bucket.mp4

The file comes to 1:05:57, or 3907 seconds. Lets extract 10 5-second clips at random and combine them to create a new video.

 ```python
import os
import random

total*time=3907
clip*time=5

def random*start():
return random.random()*(total*time-clip*time)

os.system('cd /Users/yourname/Desktop/')

for i in range(10):
os.system("ffmpeg -i Bucket.mp4 -ss "+str(random*start())+" -t 4 clip"+str(i)+".mpg")

os.system('''ffmpeg -i "concat:clip0.mpg|clip1.mpg|clip2.mpg|clip3.mpg|clip4.mpg|clip5.mpg|clip6.mpg|clip7.mpg|clip8.mpg|clip9.mpg" -c copy collage.mpg''')
```
## Python introduction
#### (11:00–11:30)
## Very basics

print "Hello Jupyter!"
print "Hello"+" Jupyter!"

### Integer Arithmetic

int1=10000
int2=150

print int1+int2 # add
print int1-int2 # subtract
print int1*int2 # multiply
print int1/int2 # divide

### Floating Point Arithmetic

float1=10000.0
float2=150.5

print float1+float2 # add
print float1-float2 # subtract
print float1*float2 # multiply
print float1/float2 # divide

## Lists

# String Manipulation
## In which we split and reassemble a sentence.

```
sentence="A green hunting cap squeezed the top of a fleshy balloon of a head."
print sentence

words=sentence.split(" ")
print words

rejoined=" ".join(words)
print rejoined

# List Slice Notation

print len(words)

print words[4]()
print words[2:5]()
print words[2:]()
print words[:2]()
print words[-4]()
print words[-4:]()
```

Lines beginning with '!' are executed in Bash, i.e., the default Unix environment you're in when you open a new Terminal window.

# The following Bash command displays your username.

!whoami

# And this one prints a list of files on your desktop.

!ls /Users/yourname/Desktop/   ### Swap in your username here. ###

# The following simplified format does the same.

# Note that this shortcut works in Bash but not in Python's 'os' module.

!ls /Desktop/

Python can execute Bash commands as well, via the os module:

# This cell imports the 'os' module, then prints a list of filenames on the desktop.

import os

os.chdir("/Users/yourname/Desktop/") ### Swap in your username here. ###
filenames = os.listdir("/Users/yourname/Desktop/")  ### Swap in your username here. ###
print filenames

# The pprint module shows us the list above in a more readable format.

from pprint import pprint

pprint(filenames)

# If your desktop is filled with screen capture files, uncomment and run the lines below 
# to create a 'Screenshots' directory and send future captures there by default.

# !mkdir /Desktop/Screenshots
# !defaults write com.apple.screencapture location /Desktop/Screenshots ; killall SystemUIServer
Basic Text I/0

In the following demonstrations we'll be loading plain text files from the Web like so:

import urllib2

url="http://principalhand.org/workshop-data/Melville_Moby-Dick.txt"

melville_string=urllib2.urlopen(url).read()

And here's how to work with text files on your local system:

# First, this Bash command creates a two-line text file on your desktop.

!echo "This is the first line.nThis is the second line." > /Desktop/testfile.txt

# The shortest format for creating a string from a text file:

text=open("/Users/yourname/Desktop/test_file.txt").read()  ### Swap in your username here. ###

print text

# Or we can work with one line at a time. Note that the newline character at the end of the
# first line ends up creating a gap when the lines are printed separately.

with open("/Users/yourname/Desktop/test_file.txt") as fi:  ### Swap in your username here. ###
for line in fi:
print line

# Load a text file as a list of lines, discarding newline characters.

line_list=open("/Users/yourname/Desktop/test_file.txt").read().splitlines()  ### Swap in your username here. ###

print line_list

# And we can write string data to a new text file like so:

fo=open("/Users/yourname/Desktop/test_file_2.txt","w")  ### Swap in your username here. ###

fo.write("This is another first line.n")
fo.write("This is another second line.")

fo.close()

# A file called "test_file_2.txt" should appear on your desktop.

### Importing a package
### os, shutil, and subprocess



