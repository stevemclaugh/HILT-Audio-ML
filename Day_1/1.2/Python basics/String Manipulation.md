# String Manipulation
## In which we split and reassemble a sentence.

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
▷ Lines beginning with '!' are executed in Bash, i.e., the default Unix environment you're in when you open a new Terminal window.

# The following Bash command displays your username.

!whoami

# And this one prints a list of files on your desktop.

!ls /Users/yourname/Desktop/   ### Swap in your username here. ##\#

# The following simplified format does the same.

# Note that this shortcut works in Bash but not in Python's 'os' module.

!ls /Desktop/
▷ Python can execute Bash commands as well, via the os module:

# This cell imports the 'os' module, then prints a list of filenames on the desktop.

import os

os.chdir("/Users/yourname/Desktop/") ### Swap in your username here. ##\#
filenames = os.listdir("/Users/yourname/Desktop/")  ### Swap in your username here. ##\#
print filenames

# The pprint module shows us the list above in a more readable format.

from pprint import pprint

pprint(filenames)

# If your desktop is filled with screen capture files, uncomment and run the lines below 
# to create a 'Screenshots' directory and send future captures there by default.

# !mkdir /Desktop/Screenshots
# !defaults write com.apple.screencapture location /Desktop/Screenshots ; killall SystemUIServer
Basic Text I/0
▷ In the following demonstrations we'll be loading plain text files from the Web like so:

import urllib2

url="http://principalhand.org/workshop-data/Melville_Moby-Dick.txt"

melville_string=urllib2.urlopen(url).read()
▷ And here's how to work with text files on your local system:

# First, this Bash command creates a two-line text file on your desktop.

!echo "This is the first line.\nThis is the second line." \> /Desktop/testfile.txt

# The shortest format for creating a string from a text file:

text=open("/Users/yourname/Desktop/test_file.txt").read()  ### Swap in your username here. ##\#

print text

# Or we can work with one line at a time. Note that the newline character at the end of the
# first line ends up creating a gap when the lines are printed separately.

with open("/Users/yourname/Desktop/test_file.txt") as fi:  ### Swap in your username here. ##\#
for line in fi:
print line

# Load a text file as a list of lines, discarding newline characters.

line_list=open("/Users/yourname/Desktop/test_file.txt").read().splitlines()  ### Swap in your username here. ##\#

print line_list

# And we can write string data to a new text file like so:

fo=open("/Users/yourname/Desktop/test_file_2.txt","w")  ### Swap in your username here. ##\#

fo.write("This is another first line.\n")
fo.write("This is another second line.")

fo.close()

# A file called "test_file_2.txt" should appear on your desktop.

