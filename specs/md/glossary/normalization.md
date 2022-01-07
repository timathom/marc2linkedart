---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: MARC to Linked Art mapping glossary
---

# Normalization

String normalization includes the following steps:

1.  Remove diacritics from the string.
2.  Convert the characters to lower case.
3.  Trim leading and trailing whitespace.
4.  Convert internal whitespace to single whitespace characters.
5.  Remove punctuation characters as specified.
    -   Punctuation characters are equivalent to the `\p{Punct}` character class in Java's regex implementation.

**Note:** See [Java regex documentation](http://www.fredosaurus.com/notes-java/data/strings/40regular_expressions/25sum-regex.html).

**Parent topic:**[MARC to Linked Art glossary](../glossary/marc_to_linked_art_glossary.md)

