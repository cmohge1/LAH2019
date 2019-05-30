# LAHP2019: "Working with Texts," part II: 30 May 2019.

Martin Steer (School of Advanced Study)

Jonathan Blaney (Institute of Historical Research)

Christopher Ohge (Institute of English Studies)

## Outline for the day 
|Topic |Time |
|--:|--:|
|[Introduction to bits, bytes, encoding etc](#Bits-and-Bytes) | 30 mins, Marty|
|[Intro the CLI: principles, navigations](#Command-Line) | 15 mins, Christopher|
|[Regex](#Regular-Expressions)| 20 mins, Christopher|
|Regex questions| 15 mins|
|[Grep and regex](#Grep) | 15 mins, Jonathan|
|Grep questions| 15 mins|
|[CLI tool for document conversion: Pandoc](#Pandoc)| 10 mins, Christopher|

### Bits and Bytes

[See Marty's slides](https://github.com/cmohge1/LAHP2019/blob/master/LAHP%202018%20Wk%204%20Working%20with%20Text.pdf).

### Command Line

Make sure you have downloaded Git (https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

1. What are command line tools, why do we use them, and which do we use most?

- **command line tools** are based on "standard" Unix commands, but also include other commands from downloadable packages (e.g., Git and Pandoc).

- generally, **we use CLI tools** to hack our system, to have full control ...

- **the CLI tools we use most** are **navigation, conversion, and system debugging**...

- use **Tab** to complete arguments or list all available commands. 

- use **ctrl+r** to search through command history.

- **navigation:**
    - `cd`
    - `.` and `..`
    - `pwd`
    - `ls`
    - `mv`
    - `mkdir`
    - `echo`
    - `less`
    - `head`
    - `tail`
    
- **conversion**
    - `iconv`
    - `grep`
    - To locate a file by name in the current directory, `find . -iname 'NAME'`
    - `awk` (line by line processing)
    - `sed` (searching and replacing)
    
- **debugging** is important, but we won't have time to do this justice.
    
- Want to learn more? Enter `man bash` into your Terminal window.

For a very good (and broad) overview of command line tools, see https://github.com/jlevy/the-art-of-command-line.


2. Exercise: Get a copy of this repository.

- Navigate to this repo (https://github.com/cmohge1/LAHP2019).

- click on the green button that says "clone or download".

- IF you have a GitHub account,
    - open your terminal, enter `cd ~/Desktop`
    - use the `git clone` function. 
    - `git clone https://github.com/cmohge1/LAHP2019.git`

- IF YOU DO NOT have a GitHub account, download the zip of the repo to your Desktop.

- in the Terminal, enter `pwd`.

- start with `cd` + ENTER.

- make a new directory called "gitspace"

- navigate to the gitspace directory, then to "LAHP2019".

- naviagte to the Billy Budd folders, and create a new folder called "diplomatic".

- move the file "ch1-leaf.xml" to "diplomatic".

- use `head` -- what do you see?

### Regular Expressions 

(AKA regex)

The best way to learn regex is to experiment with one of the online tools. But let's copy-and-paste the xml file from the Billy Budd/diplomatic directory. Then go to [Regex101](https://regex101.com/).

For more information, see this [regex cheat sheet](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285).

### Grep

See the grep basics sheet (here)[/grep-basics-sheet.pdf].

### Pandoc

Install Pandoc [here](https://pandoc.org/installing.html).

[Pandoc](https://pandoc.org/) is a very handy universal document converter. It is used on the command line following a basic syntax:

```pandoc FILE-TO-CONVERT -o CONVERTED-FILE```

We invoke pandoc first, then type out (and tab) the file we want to convert, use the -o option (which stands for output), and name the output file. That's it. 

Let's go back to our Terminal. Navigate to our git repo, type `ls`.

If we take this file (README.md), and we want to convert it to a PDF, how would we do that?

```pandoc README.md -o LAHP-working-textsII.pdf```

Most pandoc operations look like the above. There are more precise ways to guide the conversion: So if you want an html file of this README file,

```pandoc README.md -f markdown -t html -s -o README.html```

works like a charm, for the most part. The -f options specifies that you are converting from markdown syntax, and -t says that you are converting to html. The -s option specifies that it is a standalone file with a proper html header. In most cases, however, pandoc only needs the file extension to guide the conversion, which is why the -o option is all you need in most cases. But sometimes you do need more precision, such as with PDF conversions (note that you’ll need to have LaTeX installed. See MacTeX on OS X, MiKTeX on Windows, or install the texlive package in linux).

```pandoc README.md -o README.pdf```

What happens here?

Try this instead:

```pandoc -N README.md --toc -o README.pdf```

What has changed?

I have already extolled the virtues of Markdown, and I hope you can see that you can use Pandoc to easily convert files from Markdown.




