# Email Address Regular Expression Breakdown

    Regular expressions are a combination of special characters to define the accepted criteria in a search. 
    They can be quite useful for when your code needs a specific type of input or even specific string types such as an email, or url. 
    In addition they are universal in coding languages, meaning you may use them in any language. 

    Regular expressions may to the untrained eye seem like a jumble of random characters. 
    However in this breakdown we'll be going over the componenets of a regular expression to better understand how something like this

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

    Can be interpreted to only accept email addresses.


## Regex Components

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)


### Anchors
    To start a Regex is classified as a literal, meaning it will be contained between two slash characters (/). 

    Anchors mark the string for the search pattern. In our example:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

    The characters ^ and $ are anchors.

    ^ signigies the start of the string with whatever charcter follows it. 
    And $ determines the end of the string. For instance:

`/^The$/` 

    Would only accept the string "The" and is case sensitive, meaning it would not accept something like "the"


### Quantifiers

    Quantifiers are determine the limits of the matches of your regex string or a specific portion of it. 
    They are generally used to set the min and max character amounts on your regex. 
    Quantifiers go at the end of your regular expression, but before the $ anchor. In this example:

`/^[a-z0-9_-]{2,8}$/`

    The curly brackets {} sets the limit of characters of the string to be between 2 and 8.

    Some examples of some Quanitifiers are:

- `* will match the pattern zero or more times`

- `+ will match the pattern one or more times`

- `? will match the pattern zero or one time`

- `{} Curly brackets provide three ways of setting the limits for a match:`

    - `{ n } will match the pattern for exactly n number of times`

    - `{ n, } will match the pattern to a minimum of n number of times`

    - `{ n, x } will match the pattern between n and x times`

### Grouping Constructs

    If you would like to check specific parts of the regex for specific characters than you will want to use grouping constructs. 
    Grouping constructs can be used with parantheses (), for example:

`/^(the):(GUY)$/`

    the first group construct is looking for the characters t h e and in that order and case. The second construct is looking for the characters G U Y in that order and case, so this regex would not accept things like this:
- The:GUY 
- the:guy
- THE:GUY
    But would accept:
- the:GUY

### Bracket Expressions

    Bracket expressions start with, you guessed it, brackets [], 

### Character Classes


### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
