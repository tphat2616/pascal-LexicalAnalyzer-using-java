# pascal-LexicalAnalyzer-using-java

Lexical Analyzer 

In this assignment, you will write a lexical analyzer for the PASC language. The analyzer will consist of a scanner, written in Lex, and the routines to manage a lexical table.

Token Speciftcation

In PASC, not all keywords are reserved words. The table in Page 3 defines the tokens that must be recognized, with their associated symbolic names. All multi-symbol tokens are separated by blanks, tabs, newlines, comments or delimiters.
Comments are enclosed in (* ... *), and cannot be nested. An identifier is a sequence of (upper or lower case) letters or digits, beginning with a letter. Upper and lower case are not distinguished (i.e. the identifier ABC is the same as Abc). There is no limit on the length of identifiers. However, you may impose limits on the total number of distinct identifiers and string lexemes and on the total number of characters in all distinct identifiers and string taken together. There should be no other limitation on the number of lexemes that the lexical analyzer will process.
An integer constant is an unsigned sequence of digits representing a 10-based number. A character constant is a character enclosed in single quotes (e.g., ’a’ is a character constant a). A string constant is a sequence of characters surrounded by single quotes (e.g. ’Hello, world’). The internal representations of character constant and string constant are different in PASC. Hard-to-type or invisible characters can be represented in character and string constants by escape sequences; these sequences look like two characters, but represent only one. The escape sequences supported by the PASC language are \n for newline, \t for tab, \’ for the single quote and \\ for the backslash itself. Any other character follows backslash is not treated as an escape sequence.

Token attributes

A unique identification of each token (integer aliased with the symbolic token name) must be returned by the lexical analyzer. In addition, the lexical analyzer must pass extra information about some token to the parser. This extra information is passed to the parser as a single value, namely an integer, through a global variable as described below. For integer constants, the numeric value of the constant is passed. For character constants, the numeric value of the character in the local set is passed. In order to allow other phases of the compiler to access the original identifier lexeme, the lexical analyzer passes an integer uniquely identifying an identifier (other than reserved words). String constants are treated in the same way, with a unique identifying number being passed. The unique identifying number, for both identifiers and string constants, should be an index (pointer) into a string table created by the lexical analyzer to record the lexemes.

Error Handling

Your lexical analyzer should recover from all malformed lexemes, as well as such things as string constants that extended across a line boundary or comments that are never terminated.
