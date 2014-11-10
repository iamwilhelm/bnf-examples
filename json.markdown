---
title: JSON BNF grammar
---

# JSON BNF

[JSON](json.org) is a data interchange format for transmitting data.

    json = [ object eof ]

    object = [ '{' members? '}' ]

    members = [ pair [',' pair]* ]

    pair = [ string ':' value ]

    value =
    [
        string
        | number
        | object
        | array
        | "true"
        | "false"
        | "null"
    ]

    string = '"' [ char [ char ]* ] '"'

    char = any unicode character except " or \ or control-character
           | '\"'
           | '\\'
           | '\/'
           | '\b'
           | '\f'
           | '\n'
           | '\r'
           | '\t'
           | '\u' + four-hex-digits

    array = [ '[' elements? ']' ]

    elements = [ value [',' value]* ]

    number = [ @ignore("null") [int frac? exp?] ]

    int = [ '-'?
        [
            digit1_9s
            | digit
        ]
    ]

    frac = [ '.' digits ]

    exp = [ e digits ]

    digit = [ '0'..'9' ]

    digit1_9 = [ '1'..'9' ]

    digits = [ digit+ ]

    digit1_9s = [ digit1_9 digits ]

    e = [ ['e'|'E'] ['+'|'-']? ]

- [http://pythonhosted.org/pyrser/tutorial1.html](http://pythonhosted.org/pyrser/tutorial1.html)
- [verified at json.org](json.org)
