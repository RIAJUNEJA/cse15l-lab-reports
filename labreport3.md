# Lab Report 3

I choose **find** command to research on and find alternates for.

Normally, find command is cumbersome to use and not refined.


## Command 1 : `-name`

> Source:

[source](https://man7.org/linux/man-pages/man1/find.1.html)


> What it does

It refines the search and straight up displays the path where the file is found.

> Why it is useful

It saves up so much time and effort as compared to normal find command, because of its refining feature

> Examples:

```
$  find . -name 'Bahamas-History.txt'
./skill-demo1-data/written_2/travel_guides/berlitz2/Bahamas-History.txt

```

```
$  find . -name 'berlitz2'
./skill-demo1-data/written_2/travel_guides/berlitz2

```

## Command 2 : `-type`

> Source:

ChatGPT - "alternate ways to use find command bash"


> What it does

It finds files based on type

> Why it is useful

Sometimes you need to find files based on type. Instead of comparing all files, just use this command.

> Examples:

```
$ find -type d
.
./.git
./.git/info
./.git/hooks
.
.
./skill-demo1-data/written_2/travel_guides/berlitz1
./skill-demo1-data/written_2/travel_guides/berlitz2
```

This displays all files of directory type

```
$  find . -type f

```

The output was too long but it displayed all files of type file.

## Command 3 : `-size`

> Source:

ChatGPT - "alternate ways to use find command bash"


> What it does

It finds files based on size

> Why it is useful

Sometimes you need to find files based on size. Instead of comparing all files, just use this command.

> Examples:

```
$ find -size +500
./.git/objects/pack/pack-cd15105c095bef3eabe7ab46217abba163043e6c.pack
./lib/junit-4.13.2.jar
./skill-demo1-data/.git/objects/pack/pack-b98cb6a4ca64cc7b2944f0fa07d3e03927d66064.pack
./skill-demo1-data/written_2/travel_guides/berlitz1/WhereToItaly.txt
[cs15lwi23akh@ieng6-201]:skill-demo1-server:308$ 
```

```
$ find -size +5000./skill-demo1-data/.git/objects/pack/pack-b98cb6a4ca64cc7b2944f0fa07d3e03927d66064.pack

```

## Command 4 : `-mtime`

> Source:

ChatGPT - "alternate ways to use find command bash"


> What it does

It finds files based on the last date you modified it on.

> Why it is useful

This can be helpful to confirm whether and when you modified a file, etc.

> Examples:

```
$ find -mtime -7
.
./skill-demo1-data
.
.
./skill-demo1-data/written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
This was for 7 days ago

```
$find -mtime 1
```

This displayed nothing as obviously it can't look into the future.


