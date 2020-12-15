<h1 align="center">Cat, tail, less and head</h1>

<div align="center">

[![Status](https://img.shields.io/github/last-commit/Alitejawi/awk.svg?style=flat-square)](https://github.com/Alitejawi/awk/commits/master)
[![GitHub Issues](https://img.shields.io/github/issues/Alitejawi/awk.svg?style=flat-square)](https://github.com/Alitejawi/awk/issues)
[![License](https://img.shields.io/github/license/Alitejawi/awk?style=flat-square)](https://github.com/Alitejawi/awk/blob/master/LICENSE)

</div>

---

<p align="center">
💻 A collection of cat, less tail and head snippets, see Learnbyexample's Github page for more.
  <br>
</p>

* For below examples, `marks_201*` files contain 3 fields delimited by TAB
* To avoid formatting issues, TAB has been converted to spaces using `col -x` while pasting the output here

<br>

#### <a name="concatenate-files"></a>Concatenate files

* One or more files can be given as input and hence a lot of times, `cat` is used to quickly see contents of small single file on terminal
* To save the output of concatenation, just redirect stdout

```bash
$ ls
marks_2015.txt  marks_2016.txt  marks_2017.txt

$ cat marks_201*
Name    Maths   Science
foo     67      78
bar     87      85
Name    Maths   Science
foo     70      75
bar     85      88
Name    Maths   Science
foo     68      76
bar     90      90

$ # save stdout to a file
$ cat marks_201* > all_marks.txt
```

<br>

#### <a name="accepting-input-from-stdin"></a>Accepting input from stdin

```bash
$ # combining input from stdin and other files
$ printf 'Name\tMaths\tScience \nbaz\t56\t63\nbak\t71\t65\n' | cat - marks_2015.txt
Name    Maths   Science
baz     56      63
bak     71      65
Name    Maths   Science
foo     67      78
bar     87      85

$ # - can be placed in whatever order is required
$ printf 'Name\tMaths\tScience \nbaz\t56\t63\nbak\t71\t65\n' | cat marks_2015.txt -
Name    Maths   Science
foo     67      78
bar     87      85
Name    Maths   Science
baz     56      63
bak     71      65
```

<br>

#### <a name="squeeze-consecutive-empty-lines"></a>Squeeze consecutive empty lines

```bash
$ printf 'hello\n\n\nworld\n\nhave a nice day\n'
hello


world

have a nice day
$ printf 'hello\n\n\nworld\n\nhave a nice day\n' | cat -s
hello

world

have a nice day
```

<br>

#### <a name="prefix-line-numbers"></a>Prefix line numbers

```bash
$ # number all lines
$ cat -n marks_201*
     1  Name    Maths   Science
     2  foo     67      78
     3  bar     87      85
     4  Name    Maths   Science
     5  foo     70      75
     6  bar     85      88
     7  Name    Maths   Science
     8  foo     68      76
     9  bar     90      90

$ # number only non-empty lines
$ printf 'hello\n\n\nworld\n\nhave a nice day\n' | cat -sb
     1  hello

     2  world

     3  have a nice day
```

* For more numbering options, check out the command `nl`

```bash
$ whatis nl
nl (1)               - number lines of files
```

<br>