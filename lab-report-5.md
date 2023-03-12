# The Find Command
## Lab Report 5
Last time in lab report 3, I talked about four ways to use the `grep` command. As my interest grew in command-line interface, I found this as the perfect opportunity to write up another report about a different command, `find`! So here are four ways to use the `find` command.

## Type
Ever wanted to search through a directory and filter the results based on the type of file? I present to you, `-type`:

```bash
find [path] -type [filetype]
```

This option allows you to search for files or directories of a specific type. For instance, I went into the `written-2/` directory:
```bash
cd skil-demo1-data/written_2/
```
I wanted to see all the directories in the `non-fiction/` directory, so I typed:
```bash
find non-fiction/ -type d
```
In return gave me:
```
non-fiction
non-fiction/OUP
non-fiction/OUP/Abernathy
non-fiction/OUP/Berk
non-fiction/OUP/Castro
non-fiction/OUP/Fletcher
non-fiction/OUP/Kauffman
non-fiction/OUP/Rybczynski
```
As you can see, it listed all the directories in the `non-fiction/` directory. In the command, *d* represented directory. However, I could also filter it by files using *f* like so:
```bash
find non-fiction/ -type f
```
In return gave me:
```
non-fiction/OUP/Abernathy/ch1.txt
non-fiction/OUP/Abernathy/ch14.txt
non-fiction/OUP/Abernathy/ch15.txt
non-fiction/OUP/Abernathy/ch2.txt
non-fiction/OUP/Abernathy/ch3.txt
non-fiction/OUP/Abernathy/ch6.txt
non-fiction/OUP/Abernathy/ch7.txt
non-fiction/OUP/Abernathy/ch8.txt
non-fiction/OUP/Abernathy/ch9.txt
non-fiction/OUP/Berk/CH4.txt
non-fiction/OUP/Berk/ch1.txt
non-fiction/OUP/Berk/ch2.txt
non-fiction/OUP/Berk/ch7.txt
```
There is actually quite a lot more files that it gave me, but you sorta get the idea that it lists all the files in the non-fiction/ directory.
I found this command-line option when searching exactly how the find command works, [here](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/#:~:text=The%20find%20command%20is%20one,action%20on%20each%20matched%20file.)!
## Modification Time
Perhaps you wanted to filter files based on when they were created, modified, or accessed depending on a certain time range! I present to you, `-mtime`:
```bash
find [path] -mtime [number of days]
```
This option allows you to search for files based on a specific number of days since they were modified. I went ahead and played around with this using the same `non-fiction/` directory as earlier:
```bash
find non-fiction/ -mtime 1
```
In return gave me... nothing. I put 1 because I wanted to see the files that were modified within the past day or so, but upon realization, I cloned the skill-1-demo-data today! So instead, I tried:
```bash
find non-fiction/ -mtime 0
```
In return gave me:
```
non-fiction/OUP/Abernathy/ch1.txt
non-fiction/OUP/Abernathy/ch14.txt
non-fiction/OUP/Abernathy/ch15.txt
non-fiction/OUP/Abernathy/ch2.txt
non-fiction/OUP/Abernathy/ch3.txt
non-fiction/OUP/Abernathy/ch6.txt
non-fiction/OUP/Abernathy/ch7.txt
non-fiction/OUP/Abernathy/ch8.txt
non-fiction/OUP/Abernathy/ch9.txt
non-fiction/OUP/Berk/CH4.txt
non-fiction/OUP/Berk/ch1.txt
non-fiction/OUP/Berk/ch2.txt
non-fiction/OUP/Berk/ch7.txt
```
All I did was change the 1 to a 0! Indicating any files that were modified within the past zero days- today! Since I just cloned the repository, all the files are "brand new."
I found this command-line option when searching for different ways to use find, [here](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)!
## Size 
Files all have different sizes. You can use the find command to filter based on their size! I present to you: **-size**:
```bash
find [path] -size [-+][size][unit]
```
This option allows you to search for files based on their size. With the vast amount of files in the skill-demo-data, I was curious as to which files are smaller or larger:
```bash
find non-fiction/ -size -10k
```
In return gave me:
```
non-fiction/
non-fiction/OUP
non-fiction/OUP/Abernathy
non-fiction/OUP/Berk
non-fiction/OUP/Castro
non-fiction/OUP/Castro/chN.txt
non-fiction/OUP/Castro/chO.txt
non-fiction/OUP/Castro/chQ.txt
non-fiction/OUP/Castro/chW.txt
non-fiction/OUP/Castro/chY.txt
non-fiction/OUP/Castro/chZ.txt
non-fiction/OUP/Fletcher
non-fiction/OUP/Kauffman
non-fiction/OUP/Rybczynski
```
It is interesting how it gave me directories as well! In the command, the `-` means anything smaller, `10` is the size, and `k` is the unit (kilobytes). So I looked in the `non-fiction/` directory for *anything* less than 10 kilobytes. If we used the `-type` option, we can single out just the files. Anyhow, let's bump up the size and look for larger files:
```bash
find non-fiction/ -size -50k
```
In return gave me:
```
non-fiction/
non-fiction/OUP
non-fiction/OUP/Abernathy
non-fiction/OUP/Abernathy/ch1.txt
non-fiction/OUP/Abernathy/ch14.txt
non-fiction/OUP/Abernathy/ch15.txt
non-fiction/OUP/Abernathy/ch2.txt
non-fiction/OUP/Abernathy/ch3.txt
non-fiction/OUP/Abernathy/ch6.txt
non-fiction/OUP/Abernathy/ch7.txt
non-fiction/OUP/Abernathy/ch9.txt
non-fiction/OUP/Berk
non-fiction/OUP/Castro
non-fiction/OUP/Castro/chA.txt
non-fiction/OUP/Castro/chB.txt
non-fiction/OUP/Castro/chC.txt
non-fiction/OUP/Castro/chL.txt
non-fiction/OUP/Castro/chN.txt
non-fiction/OUP/Castro/chO.txt
non-fiction/OUP/Castro/chP.txt
non-fiction/OUP/Castro/chQ.txt
non-fiction/OUP/Castro/chR.txt
non-fiction/OUP/Castro/chV.txt
non-fiction/OUP/Castro/chW.txt
non-fiction/OUP/Castro/chY.txt
non-fiction/OUP/Castro/chZ.txt
non-fiction/OUP/Fletcher
non-fiction/OUP/Fletcher/ch1.txt
non-fiction/OUP/Fletcher/ch10.txt
non-fiction/OUP/Fletcher/ch5.txt
non-fiction/OUP/Kauffman
non-fiction/OUP/Kauffman/ch5.txt
non-fiction/OUP/Kauffman/ch7.txt
non-fiction/OUP/Rybczynski
non-fiction/OUP/Rybczynski/ch1.txt
non-fiction/OUP/Rybczynski/ch2.txt
```
Now there are a whole lot more files and directories. It is quite interesting, as now we have a way to separate which chunks of a directory are smaller or larger, as the results above are all less than 50 kilobytes.
I found this command-line option after coming across an article describing how to find the largest files in your linux operating system, [here](https://www.cyberciti.biz/faq/how-do-i-find-the-largest-filesdirectories-on-a-linuxunixbsd-filesystem/)!

## Empty
Perhaps you have a ton of files that you wanna clean up, but you want to be careful. You can use: **-empty**:
https://www.geeksforgeeks.org/find-command-in-linux-with-examples/
```bash
find [path] -empty
```
This option allows you to search for empty files or directories.
```bash
grep -c "Italy" ./written_2/travel_guides/berlitz1/WhereToItaly.txt
```
