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
- [Character Escapes](#character-escapes)
- [Conclusion](#conclusion)
- [Author](#author)


### Anchors
    To start a Regex is classified as a literal, meaning it will be contained between two slash characters ( / ). 

    Anchors mark the string for the search pattern. In our example:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

    The characters ^ and $ are anchors.

    ^ signigies the start of the string with whatever charcter follows it. 
    And $ determines the end of the string. For instance:

`/^The$/` 
<!--  -->
    Would only accept the string: 
<!--  -->
- "The"
 <!--  -->
    and is case sensitive, meaning it would not accept something like: 
<!--  -->
- "the"


### Quantifiers

    Quantifiers are determine the limits of the matches of your regex string or a specific portion of it. 
    They are generally used to set the min and max character amounts on your regex. 
    Quantifiers go at the end of your regular expression, but before the $ anchor. In this example:

`/^[a-z0-9_-]{2,8}$/`

    The curly brackets `{}` sets the limit of characters of the string to be between 2 and 8.

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
    Grouping constructs can be used with parantheses `()`, for example:

`/^(the):(GUY)$/`

    The first group construct is looking for the characters t h e and in that order and case. 
    The second construct is looking for the characters G U Y in that order and case, 
    so this regex would accept things like this:
- the:GUY
<!--  -->
    But would not accept:
<!--  -->
- The:GUY 
- the:guy
- THE:GUY
<!--  -->

### Bracket Expressions

    Bracket expressions start with, you guessed it, brackets `[]`.
    Anything within the brackets represents what kind of characters may go in the string.
    This type of pattern is known as a postitve character group.
    For example:
<!--  -->
`/^[kdf]$/`
<!--  -->
    Will accept:
<!--  -->
- kdf
- fdk
- kkdkffdkfkd
    But will not accept:
- kdef
- Kdf
- KDF

    Furthermore brackets expressions oftentimes contain a hyphen `(-)` between characters.
    This hyphen is used to express the range of acceptable characters.
    For example:
<!--  -->
`/^[d-k2-9]$/`
<!--  -->
    Will accept:
<!--  -->
- dk2
- defghijk
- egh
<!--  -->
    But will not accept:
<!--  -->
- adk
- dk1
- Dk

    Bracket expressions can also be made into negative charater groups by adding the ^ symbol after the start of the opening bracket.
    This will make them look for any string that is exlduing those specificed characters in the brackets.

### Character Classes

    A character class is a shortcut for a group of characters ranges. 
    Some examples are:
<!--  -->
- . will select any character except the newline character `(\n)`

- \d will select any arabic number, can be treated the same as `[0-9]`

- \w will select with any alphanumerical character and underscore `_` , can be treated the same as `[A-Za-z0-9_]`

- \s will select a single whitespace character, including tabs and line breaks
<!--  -->

    Something to note, the last three classes can be changed to negative character groups by capitalizing the letter like
<!--  -->
- \D
- \W
- \S

### Character Escapes

    You may have asked how do we include characters such brackets or slashes then?
    This is where character escapes come in.
    By using backslash ( \ ) we are able to interpret the following character literally.
    This can be applied to backslash as well.
    For example:
<!--  -->
`/^\$$/`
<!--  -->
    Will now accept the $ symbol as a string


### Conclusion

    So now when we reexamine the regex for an email address:
<!--  -->
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
<!--  -->

    We can divide it into its group constructs 
<!--  -->
- `([a-z0-9_\.-]+)`
- `([\da-z\.-]+)`
- `([a-z\.]{2,6})`
<!--  -->
    And observe the the `@` `.` symbols dividng segments of the email address.
    Within these group constructs we can see bracket expressions and within them:
    A Character class:
<!--  -->
- `\d`
<!--  -->
    A Quantifier:
<!--  -->
- `{2,6}`
<!--  -->
    And a Character Escape
<!--  -->
- `\.`
<!--  -->
    And combined they form the Regular Expression that will only accept strings in email format.

## Author

If you'd like to check out some of my other work here is a link to my github:

[Pherenzia](https://github.com/pherenzia)