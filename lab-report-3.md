# The Grep Command
## Recursive Search 🔎
Ever had a huge directory of files, but you just wanted to locate a file containing a particular word? I present to you, **-r**:

`grep -r "string" /directory`

Sometimes the file we want can be in a folder that is in a folder that is in a folder and it goes on forever! You wouldn't want to do 
`grep string /directory/folder/folder/folder/folder/folder`... It is a bit of a hassle!

When preparing for the skill demo, I had to find the string *Lucayans*. I had no idea what the directory was to get there, 
but I did not want to explore through the files. So I searched how to use grep recursively, and I found this post [here](https://stackoverflow.com/questions/1987926/how-do-i-recursively-grep-all-directories-and-subdirectories)! In the terminal I
did the following:

`grep -r "Lucayans" . -l`

In return gave me:

`./written_2/travel_guides/berlitz2/Bahamas-History.txt`

It saved me a ton of time and work! The command searched for the string *Lucayans* in the current folder, `.` and kept searching for the string
over and over within the subfolders, **recursively searching!** The `-l` reduces a ton of output by only showing the directory. Without it, it will
show entire paragraphs that contain the string.

## Line Numbers 🔢
grep - n
https://www.techrepublic.com/article/10-ways-to-use-grep-to-search-files-in-linux/

## Specific Amount of Matches 📋
grep -m
https://www.techrepublic.com/article/10-ways-to-use-grep-to-search-files-in-linux/

## Number of Lines with Pattern 📟
grep -c
https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/
