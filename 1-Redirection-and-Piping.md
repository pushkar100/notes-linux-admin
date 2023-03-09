# Redirection & Pipelining: 

Source: http://linuxcommand.org/lts0060.php

- [Redirection & Pipelining:](#redirection---pipelining-)
  * [Redirection:](#redirection-)
    + [Standard Output:](#standard-output-)
    + [Standard Input:](#standard-input-)
  * [Pipes:](#pipes-)
  * [Filters: (Google each filter to learn more about them)](#filters---google-each-filter-to-learn-more-about-them-)

## Redirection:

### Standard Output:

Most command line programs that display their results do so by sending their results to a facility called standard output. 

By default, standard output directs its contents to the display. 

To redirect standard output to a file, the `>` character is used like this:

Ex:
- `ls > file_list.txt` = The output of `ls` command is written to the file mentioned (Contents of file overwritten)
- `ls >> file_list.txt` = Don't want to overwrite existing file contents but APPEND TO file contents.

If file does NOT exist, it is created.

### Standard Input:

Many commands can accept input from a facility called standard input. 

By default, standard input gets its contents from the keyboard, but like standard output, it can be redirected. 

To redirect standard input from a file instead of the keyboard, the `<` character is used like this:

Ex:
- `sort < sample.txt` = The input for the sort command is taken from the sample.txt (contents of the file is input)

**Redirection of both input and output:**
Ex:
- `sort < file_list.txt > sorted_file_list.txt` = Input for sort command is from file_list.txt and output of the sort command is redirected to the file sorted_file_list.txt (new or existing).

## Pipes:

By far, the most useful and powerful thing you can do with I/O redirection is to connect multiple commands together with what are called pipes. 

With pipes, the Standard Output of one command is fed into the Standard Input of another. Pipes are represented with `|`.

Good Ex:
- `ls -l | less` = The output of the ls command is fed into the less command(as standard input). 

By using this `<previouscommand(s)> | less` trick, you can make any command have scrolling output. We can use this technique all the time.

**Example: Outputting to multiple Files:**

Use `tee` command: Copy standard input to each FILE, and also to standard output.

Syntax: `tee [OPTION]... [FILE(s)]...`

Ex: 
- `tee file1 file2 file3`   = Waits for user input (ended with CTRL-C) and puts the input to `file1`, `file2`, and `file3`.
- `ls -l | tee file1 file2` = Takes output of `ls -l` and puts it into the files `file1` and `file2`.

## Filters: (Google each filter to learn more about them)

One class of programs you can use with pipes is called `filters`. 

Filters take standard input and perform an operation upon it and send the results to standard output. In this way, they can be used to process information in powerful ways. Here are some of the common programs that can act as filters:

**Common filters**

- `sort`  = Sorts standard input then outputs the sorted result on standard output.
- `uniq`  = Given a sorted stream of data from standard input, it removes duplicate lines of data (i.e., it makes sure that every line is unique).
- `grep`  = Examines each line of data it receives from standard input and outputs every line that contains a specified pattern of characters.
- `fmt`   = Reads text from standard input, then outputs formatted text on standard output.
- `pr`    = Takes text input from standard input and splits the data into pages with page breaks, headers and footers in preparation for printing.
- `head`  = Outputs the first few lines of its input. Useful for getting the header of a file.
- `tail`  = Outputs the last few lines of its input. Useful for things like getting the most recent entries from a log file.
- `tr`    = Translates characters. Can be used to perform tasks such as upper/lowercase conversions or changing line termination characters from one type to another (for example, converting DOS text files into Unix style text files).
- `sed`   = Stream editor. Can perform more sophisticated text translations than tr.
- `awk`   = An entire programming language designed for constructing filters. Extremely powerful.

USE `man` to find out more about the filters.
