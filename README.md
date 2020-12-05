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