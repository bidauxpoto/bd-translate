# bd-translate
bioinformatic and data analysis power tool to convert and integrate data (i.e. left outer join with steroids)

```
Usage: translate [options] DICTIONARY 1 2 3 < TAB_FILE 

Options:
        -f N            specify what is the column (by its number) of DICTIONARY that contains the keys to be translated in TAB_FILE [default is column 1]
        -a              append translation: add new columns with translation on the right of the translated column (instead of substituting it)
        -r              put the added columns at the end of all TAB_FILE columns
        -i              ignore empty fields in column to be translated in TAB_FILE and keep the input row as is [NB: that row will have a different number of fields if used with -a option. Consider instead to suppress the row using -k]
        -k              kill untranslated rows (because of KEY missing in DICTIONARY)
        -d              allow duplicated keys in DICTIONARY
          -g GLUE       indicate the separator for multiple values of the same key in output (when there are duplicated translations for the SAME KEY, list them in the same row, separated by GLUE)
          -j            join like out (when there are duplicated translations for the SAME KEY, generate multiple rows clustered together, one for each translation)
        -m GLUE         if the DICTIONARY file has more than 2 columns, the translation is multi-column and the separator is GLUE (different from -j because double tanslations are on the same row here) [default glue is ';']
        -b FILE         print the killed rows of STDIN/TAB_FILE in FILE
        -v              allow missing translations in the dictionary (print also rows of TAB_FILE whose value to be translated is not in the dictionary)
          -e VALUE      use VALUE as translation when a key is not present in dictionary [must be used together with -v]
        -p REGEXP       ignore input rows matching REGEXP (in Perl syntax), e.g. use -p '^>' to skip the translation of FASTA headers
        -c              case insensitive (ignore case in the comparison with the dictionary)
        -w              translate each word (word = each string of letters, numbers and/or underscores ('_'). Words can be separated by spaces (' '), hyphens ('-'), dots('.'), tabs etc [NOT compatible with column indication nor with options -a, -k]
        -s              split separator
        -z              allow dictionary to be empty
        -n              invert columns of DICTIONARY (same as -f 2) [compatibile with -m]
```
