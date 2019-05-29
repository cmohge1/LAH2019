# LAHP2019
"Working with Texts," part II: 30 May 2019.

## Outline for the day 
|Topic |Time |
|--:|--:|
|[Introduction to bits, bytes, encoding etc](#Bits-and-Bytes) | 30 mins, Marty|
|[Intro the CLI: principles, navigations](#Command-Line) | 15 mins, Christopher|
|[Grep](#Grep) | 15 mins, Jonathan|
|Grep questions| 15 mins|
|[Regex, using grep](#Regular-Expressions(RegEx))| 20 mins, Christopher|
|Regex questions| 15 mins|
|[CLI tool for document conversion: Pandoc](#Pandoc)| 10 mins, Christopher|

### Bits and Bytes

[See Marty's slides]

### Command Line

1. Make sure you have downloaded Git (https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

2. Get a copy of this repository.

- use the `git clone` function. 

`git clone`

For a very good (and broad) overview of command line tools, see https://github.com/jlevy/the-art-of-command-line.

### Grep

### Regular Expressions (RegEx)

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

I have already extolled the virtues of Markdown, and I hope you can see that you can use Pandoc to easily convert files from Markdown.




