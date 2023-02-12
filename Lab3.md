# Lab Report #3
This report contains some interesting ways to use the `grep` command. All commands were run on data inside the `written_2` directory from the skill demo data repository.
## Different Ways to Use the `Grep` Command
The `grep` command is a command line utility for UNIX-based systems that searches for a string of characters in several files. A basic example of a `grep` command that search for `Lucayans` in `Bahamas-History.txt` would be:
```
grep "Lucayans" travel_guides/berlitz2/Bahamas-History.txt
``` 
There are also some other flags/options you can add to grep to make it more powerful. Here are some examples.
### Example #1: Colorizing the results
To highlight the text that you searched for in the line that got returned, you can use the `--color` option. The --color option is helpful because oftentimes grep returns lots of text and it can be hard to find the search term you wanted. With `--color` you can find that term easily since it will stand out. 

An example which highlights all instances of `Lucayans` in the file `Bahamas-History.txt` is:
```
$ grep --color "Lucayans" travel_guides/berlitz2/Bahamas-History.txt
```
which would return this:
![--color](https://user-images.githubusercontent.com/56090826/218331243-84a50e00-70d0-4047-8ee1-12b4ba149a33.png)

Another example which highlights all instances of `January` in the file `Bermuda-WhereToGo` would be:
```
$ grep --color "January" travel_guides/berlitz2/Bermuda-WhereToGo.txt
```
which would return this:
![--color2](https://user-images.githubusercontent.com/56090826/218331254-4495e48b-a808-410d-a272-25cedd9dc3ac.png)

*[Source](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)*
### Example #2: Recursively searching all directories
The previous examples have only searched one file, but if you want to recurively search all directories and subdirectories inside a folder, you can the `-r` option. This is useful because often you have many files that you want to look through, but it would be far too cumbersome to search each one manually.

An example which searches all files and subdirectories of `written_2/` for `Lucayans` would be: 
```
$ grep -r "Lucayans" *
```
which would generate an output of:
![-r](https://user-images.githubusercontent.com/56090826/218331252-47bc94c6-9980-41c9-8195-e747b9277162.png)

Another example which searches all files and subdirectories of `non-fiction` for `Modernism` would be:
```
$ grep -r "Modernism" non-fiction
```
which would generate an output of:
![-r2](https://user-images.githubusercontent.com/56090826/218331253-b0a789b1-40b9-4304-87e0-b0bc7d8b0a7e.png)

*[Source](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)*
### Example #3: Eliminating case sensitivity
So far, all of our searches have been case sensitive meaning that searching for `Boat` would return different results than searching for `boat`. This is because, by default, `grep` is case sensitive. However, if we add the `-i` option, then our search will ignore case sensitivity. This option is often used because you want to find the word you are searching for, regardless of whether it is capitalized or not. 

An example which searches all files in `written_2/` for `Modernism` without case sensitivity would be:
```
$ grep -r -i "Modernism" *
```
which would generate an outpout of:
![-i](https://user-images.githubusercontent.com/56090826/218331255-840f6fdb-86f5-47b0-9e6a-fdc750a3890c.png)
Note that is has been truncated to save space, but there are far more results than our previous search for `Modernism` because it is picking up `modernism` as well.

Another example which searches all files in `written_2/` for `Oyez` without case sensitivity would be:
```
$ grep -r -i "Oyez" *
```
which would generate an output of:
![-i2](https://user-images.githubusercontent.com/56090826/218331256-512ecb05-cdbd-48e7-836b-c4ea95edb706.png)
Note that when a search term only appears capitalized, the `i` flag functions the same as if we had not used it.

*[Source](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)*
### Example #4: Only printing the file name
If instead of printing the text where the string appears in the file, we can also print just the file name with the `l` option. This can be useful if we are planning to do something the file rather than wanting to know the context that the string appeared in.

An example that shows all files in `written_2/` containing `Lucayans` would be:
```
$ grep -r -l "Lucayans" *
```
which would generate an output of:
![-l](https://user-images.githubusercontent.com/56090826/218331250-edc33b1a-f090-4bba-9352-18df51f17140.png)

Another example that shows all files in `written_2/` containing `Modernism` would be:
```
$ grep -r -l "Modernism" *
```
which would generate an output of:
![-l2](https://user-images.githubusercontent.com/56090826/218331251-916b6838-8f82-4f45-b2c5-5dc137af2081.png)

*[Source](https://www.gnu.org/software/grep/manual/grep.html#Command_002dline-Options)*
