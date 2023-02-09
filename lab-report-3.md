# The Grep Command
## Recursive Search 🔎
Ever had a huge directory of files, but you just wanted to locate a file containing a particular word? I present to you, **-r**:

```bash
grep -r "string" /directory/file
```

Sometimes the file we want can be in a folder that is in a folder that is in a folder and it goes on forever! You wouldn't want to do 
`grep string /directory/folder/folder/folder/folder/folder`... It is a bit of a hassle!

When preparing for the skill demo, I had to find the string *Lucayans*. I had no idea what the directory was to get there, 
but I did not want to explore through the files. So I searched how to use grep recursively, and I found this post [here](https://stackoverflow.com/questions/1987926/how-do-i-recursively-grep-all-directories-and-subdirectories)! In the terminal I
did the following:

```bash
grep -r "Lucayans" -l
```

In return gave me:

```bash
./written_2/travel_guides/berlitz2/Bahamas-History.txt
```

It saved me a ton of time and work! The command searched for the string *Lucayans* in the current folder and kept searching for the string
over and over within the subfolders, **recursively searching!** The `-l` reduces a ton of output by only showing the directory. Without it, it will
show entire paragraphs that contain the string.

Perhaps you just wanna see the pieces of text itself? In the terminal I tried:

```bash
grep -r "San Diego"
```

In return gave me:

```bash
./written_2/travel_guides/berlitz2/California-WhereToGo.txt:Cabrillo National Monument, situated on the Point Loma promontory (I-5/I-8 exit on Rosecrans Street and follow the signs), celebrates the man who discovered San Diego Bay. You can walk the trails around the point, visit the Old Point Loma Lighthouse, and at low tide explore the tide pools for crabs, starfish, anemone, and, if you are lucky, perhaps even the odd, elusive octopus. If you’re here between December and March, watch for migrating gray whales from the look-out point near the lighthouse.
./written_2/travel_guides/berlitz2/California-WhereToGo.txt:San Diego’s beaches are truly beautiful and remarkably unspoiled, stretching for some 27 miles (43 km) up to the elegant suburb of La Jolla (pronounced “la HOY-a,” Spanish for “jewel”), whose centerpiece is the tiny rock basin of La Jolla Cove. The rocky coast to the south is marvelous for walking, and away from the ocean there are stylish shops and elegant restaurants to visit. The marine life of southern California is splendidly displayed in the Birch Aquarium at Scripps, which is spectacularly sited on the hilltop above La Jolla.
```

I actually received tons of more text, but I chose these two lines to show you. As you can see, you can use `-r` to recursive search through multiple folders, whether searching for the directory or searching for the pieces of text itself.

## Line Numbers 🔢
Perhaps you want to know what line number a certain line of text is on? I present to you, `-n`:

```bash
grep -n "string" /directory/file
```

You might not want to read an entire article, but you wanna see what it has to say about the beautiful city of *San Diego*? You can find the line number like so:

```bash
grep -n "San Diego" Vallarta-WhereToGo.txt
```

In return gave me:

```
86:One of Acapulco’s historic landmarks is the Fuerte de San Diego, originally built in 1616 to protect against pirate attacks, and later renovated following extensive earthquake damage in 1776. Acapulco’s most notable museum, Museo Histórico de Acapulco, is now located in this structure, chronicling Acapulco’s exotic history as a trading port. The fort is located up a hill and to the right of the zocalo, just off the Costera.
```

As you can see, the number **86** is the line number that the sentence regarding *San Diego* is on.

Going back to the beginning, you can combine different command-line options, like recursive searching! You can find both the line numbers and directories using `-n` and `-r`:

```bash
grep -n "United States of America" -r
```
In return gave me:
```
written_2/non-fiction/OUP/Fletcher/ch1.txt:74:We the people of the United States, in order to form a more perfect Union, establish justice, insure domestic Tranquility, provide for the common defense, promote the general Welfare, and secure the Blessings of Liberty to ourselves and our Posterity, do ordain and establish this Constitution for the United States of America.
written_2/non-fiction/OUP/Fletcher/ch2.txt:14:United States of America the eighty-seventh.
written_2/travel_guides/berlitz1/WhereToHongKong.txt:704:        United States of America, put their names to a historic document — the
```
We are given the directory that the string *United States of America* is in, as well as the line number that they reside on like **74**,**14**,**704**.
I found this command-line option after searching different ways to use grep [here](https://www.techrepublic.com/article/10-ways-to-use-grep-to-search-files-in-linux/).

## Specific Amount of Matches 📋
One thing I have learned after using commands these past two weeks is the ridiculous amount of text that will show up on your screen, unless you use something like `-l`. With grep in particular, you can reduce the amount of results you want using `-m`:

```bash
grep -m$ "string" /directory/file
```
You replace the $ with the `max number` of files you want. For instance, wanting to find a maximum of 2 text files showing *San Diego*:

```bash
grep -m2 "San Diego" ./written_2/travel_guides/berlitz1/*.txt
```
In return gave me:

```
./written_2/travel_guides/berlitz1/WhatToLasVegas.txt:        outfit — is a farm team for baseball’s San Diego Padres;tickets are
./written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:        seaside Santa Barbara to the north and sunny but bustling San Diego to
./written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:        world-famous attractions as the San Diego Zoo, the San Diego Wild
```
You may be thinking, I asked for 2 text files but 3 lines showed up! The `-m` command-line option gives us a maximum number of files, but not results. With 2 of those files being the same, we technically only received 2 files. Here's another example, I just wanna find a maximum of 5 text files:

```bash
grep -m5 "Word" ./written_2/travel_guides/berlitz1/*.txt
```
In return gave me:
```
./written_2/travel_guides/berlitz1/HistoryLakeDistrict.txt:        and its lifestyle. William Wordsworth, the most famous of the group,
./written_2/travel_guides/berlitz1/HistoryLakeDistrict.txt:        Keswick. This appalled Wordsworth, who said that the Lake District
./written_2/travel_guides/berlitz1/IntroLakeDistrict.txt:        of influential local men, including poet William Wordsworth, into
./written_2/travel_guides/berlitz1/IntroLakeDistrict.txt:        Gowbarrow Park, immortalized by Wordsworth, has its “host of golden
./written_2/travel_guides/berlitz1/WhereToItaly.txt:        19th-century poets — Words­worth, Shelley, and Byron — retains a
./written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt:        follow suit. The library absorbed the Ambleside Book Club (Wordsworth
./written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt:        to William Wordsworth and his sister Dorothy in 1799. The surrounding
./written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt:        Dove Cottage was their first home. Wordsworth loved the place and wrote
./written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt:        larger home on the other side of the village. The Wordsworth Trust now
./written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt:        friends. Behind the cottage, the Wordsworth Museum displays many of
```
Here are 10 results that show files with the string *Word*. Repeats excluded though, there are a total of 4 files that showed up! 4? That means only 4 files exist, even though we asked for a maximum of 5. Like `-n`, I found `-m` when looking for different ways to use grep, [here](https://www.techrepublic.com/article/10-ways-to-use-grep-to-search-files-in-linux/)!

## Number of Lines with Pattern 📟
Okay, maybe you don't wanna know the directory a *string* is on, maybe you just wanna know how many instances the *string* will show up? Lastly, I present to you, `-c`:
```bash
grep -c "string" /directory/file
```
I set my directory to the `WhereToItaly.txt` file so I can see how many times *Italy* will pop up:
```bash
grep -c "Italy" ./written_2/travel_guides/berlitz1/WhereToItaly.txt
```
In return gave me:
```
78
```
That is all. 78 times. *Italy* shows up 78 times. In another instance, I wanted to see how many times a period . will show up in the chapter of a book:
```bash
grep -c "." written_2/non-fiction/OUP/Abernathy/ch1.txt
```
In return gave me:
```
74
```
Only 74 periods? You would think a chapter of a book would have tons of more periods. Anyhow, I found this command-line option on a different website [here](https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/), when searching for different ways to use grep.
