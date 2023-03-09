# `grep` Command:

## Introduction:

Searching for terms within a file or across multiple files? - Use `grep` command.

## `grep` Command and Options:

- `grep 'searchTerm' filePath` = Searches for the search term within the mentioned file.

- `grep 'searchTerm' *` = Searches for the search term across all the files present in the Current Working Directory.

(Note: `grep` does **NOT** search for terms within files inside directories that are part of PWD)

- `grep 'searchTerm' directoryPath/*` = Searches for the search term across all the files present in the Mentioned in the Directory

- `grep -r 'searchTerm' directoryPath/*` = Searches RECURSIVELY for the term inside specified directory including searching all subdirectory's files

- `grep -r 'searchTerm' .` = Searches RECURSIVELY for the term inside CURRENT directory including searching all subdirectory's files

**(OR)**

- `grep -r 'searchTerm' *` = Searches RECURSIVELY for the term inside CURRENT directory including searching all subdirectory's files

- `grep -n 'searchTerm' filePath` = Shows matches for the search term along with the Line Number.

- `grep -l 'searchTerm' filePath` = Shows only matched files for the search term but does not display content where it appears(only file names)

- `grep -v 'searchTerm' filePath` = Shows Lines(contents of lines) of matched files that DO NOT contain the search term (reverse of the usual grep)

- `grep -i 'searchTerm' filePath` = Shows matched lines for the search term in matched files by IGNORING CASE.

Use `-i` option to ignore case of search term while matching.

## Source of the Notes:

Source = https://www.youtube.com/watch?v=3w7xrQWRYrU
