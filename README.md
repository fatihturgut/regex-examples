# Regular Expressions in Javascript
Learn **Regular Expressions**, aka **regex** or **regexp**, by inspecting the various examples.

![Regex](https://github.com/fatihturgut/regex-examples/blob/master/regex.png)

## Getting Started
#### Creating a Regex in JavaScript
* Regular Expressions are Objects.
* There are two ways to create regex Objects
```javascript
const regex1 = new RegExp(“hello”);
const regex2 = /hello/;
```
* Once you have a regex object, you can use the one one of the methods on regex constructor like test(), exec(), etc.

#### Regex Methods
* `test()` returs true if pattern is found in the passed string; false if not.
* `exec()` returns an array of matches.
* `toString()` returns a string of the regular expression syntax.

#### String Methods
* `match()` returns an array of matches just like exec on regex.
* `search()` returns an index of the matched string.
* `replace()` replaces matches with a string.
* `split()` splits a string into an array. The division is based on the regular expression pattern.

#### Regex Flags
* It can be used as `/pattern/flags;` or `new RegExp("pattern”, "flags");`
* `g` - global, match more than one occurance.
* `i` - case insensitive match, upper or lower case doesn’t matter.
* `m` - multi-line match.

## Examples

#### 1. Using the Regex Test Method
```javascript
var string = "The dog chased the cat";
var regex = /the/;
var result = regex.test(string);
console.log(result); // true
```

#### 2. Match Literal Strings
```javascript
var string = "Hello World";
var regex = /Hello/;
var result = regex.test(string);
console.log(result); // true
```

```javascript
var string = "hello World";
var regex = /Hello/;
var result = regex.test(string);
console.log(result); // false
```

#### 3. Match a Literal String with Different Possibilities (or operator)
```javascript
var string = "Jhonny has cat and dog.";
var regex = /cat|dog|bird/;
var result = regex.test(string);
console.log(result); // true
```

#### 4. Ignore Case While Matching
```javascript
var string = "davidBeckham";
var regex = /davidbeckham/i;
var result = regex.test(string);
console.log(result); // true
```

#### 5. Extract Matches
```javascript
var string = "Extract the word 'coding' form this string";
var regex = /coding/;
var result = string.match(regex);
console.log(result); // ["coding", index: 18, input: "Extract the word 'coding' form this string 'coding'", groups: undefined]
```

#### 6. Find More Than the First Match, Multiple Match (g flag)
```javascript
var string = "Repeat, Repeat, Repeat";
var regex = /Repeat/g;
var result = string.match(regex);
console.log(result); // ["Repeat", "Repeat", "Repeat"]
```

#### 7. Find More Than the First Match, Multiple Match (i g flags)
```javascript
var string = "Repeat, repeat, repeat";
var regex = /repeat/ig;
var result = string.match(regex);
console.log(result); // ["Repeat", "repeat", "repeat"]
```

#### 8. Match Anything with Wildcard Period
```javascript
var string = "release, repeat, revert";
var regex = /re./g;
var result = string.match(regex);
console.log(result); // ["rel", "rep", "rev"]
```

```javascript
var string = "fun, sun, run";
var regex = /.un/g;
var result = string.match(regex);
console.log(result); // ["fun", "sun", "run"]
```

```javascript
var string = "how is that so hot?";
var regex = /h.t/g;
var result = string.match(regex);
console.log(result); // ["hat", "hot"]
```

#### 9. Match Single Character with Multiple Possibilities
```javascript
var string = "bag, big, bug";
var regex = /b[aiu]g/g;
var result = string.match(regex);
console.log(result); // ["bag", "big", "bug"]
```

```javascript
var string = "Beware of bugs in the abOve code.";
var regex = /[aeiou]/g;
var result = string.match(regex);
console.log(result); // ["e", "a", "e", "o", "u", "i", "e", "a", "o", "e", "o", "e"]
```

```javascript
var string = "Beware of bUgs in the abOve code.";
var regex = /[aeiou]/ig;
var result = string.match(regex);
console.log(result); // ["e", "a", "e", "o", "U", "i", "e", "a", "O", "e", "o", "e"]
```

#### 10. Match Letters of the Alphabet
```javascript
var string = "The quick brown fox jumps over the lazy dog.";
var regex = /[a-z]/ig;
var result = string.match(regex);
console.log(result); // ["T", "h", "e", "q", "u", "i", "c", "k", "b", "r", "o", "w", "n", "f", "o", "x", "j", "u", "m", "p", "s", "o", "v", "e", "r", "t", "h", "e", "l", "a", "z", "y", "d", "o", "g"]
```

#### 11. Match Numbers and Letters of the Alphabet
```javascript
var string = "Number pi is 3.14159265359.";
var regex = /[2-6h-s]/ig;
var result = string.match(regex);
console.log(result); // ["N", "m", "r", "p", "i", "i", "s", "3", "4", "5", "2", "6", "5", "3", "5"]
```

#### 12. Match Single Characters Not Specified
```javascript
var string = "3 blind mice.";
var regex = /[^0-9aeiou]/ig;
var result = string.match(regex);
console.log(result); // [" ", "b", "l", "n", "d", " ", "m", "c", "."]
```
#### 13. Match Characters that Occur One or More Times
```javascript
var string = "Mississippi";
var regex = /s+/g;
var result = string.match(regex);
console.log(result); // ["ss", "ss"]
```

```javascript
var string = "Mississippi is a state of the United States.";
var regex = /s+/g;
var result = string.match(regex);
console.log(result); // ["ss", "ss", "s", "s", "s"]
```

#### 14. Match Characters that Occur Zero or More Times
```javascript
var string = "gooooooooal!";
var regex = /go*/;
var result = string.match(regex);
console.log(result1); // ["goooooooo", index: 0, input: "gooooooooal!", groups: undefined]
```

```javascript
var string = "feels good";
var regex = /go*/;
var result = string.match(regex);
console.log(result); // ["goo", index: 6, input: "feels good", groups: undefined]
```

```javascript
var string = "over the moon";
var regex = /go*/;
var result = string.match(regex);
console.log(result); // null
```

```javascript
var string = "Aaaaarrghhh!";
var regex = /Aa*/;
var result = string.match(regex);
console.log(result); // ["Aaaaa", index: 0, input: "Aaaaarrghhh!", groups: undefined]
```


#### 15. Find Characters with Lazy Matching
```javascript
var string = "titanic";
var regex = /t[a-z]*i/;
var result = string.match(regex);
console.log(result); // ["titani", index: 0, input: "titanic", groups: undefined]
```

```javascript
var string = "titanic";
var regex = /t[a-z]*?i/;
var result = string.match(regex);
console.log(result); // ["ti", index: 0, input: "titanic", groups: undefined]
```

```javascript
var string = "<h1>Winter is comming</h1>";
var regex = /<.*>/;
var result = string.match(regex);
console.log(result); // ["<h1>Winter is comming</h1>", index: 0, input: "<h1>Winter is comming</h1>", groups: undefined]
```

```javascript
var string = "<h1>Winter is comming</h1>";
var regex = /<.*?>/;
var result = string.match(regex);
console.log(result); // ["<h1>", index: 0, input: "<h1>Winter is comming</h1>", groups: undefined]
```

#### 16. Find One or More Criminals in a Hunt
```javascript
var string = "P1P2P3P4P4P5CCCP7P8P9";
var regex = /C+/;
var result = string.match(regex);
console.log(result); // ["CCC", index: 12, input: "P1P2P3P4P4P5CCCP7P8P9", groups: undefined]
```

#### 17. Match Beginning String Patterns
```javascript
var string = "John and Ricky Both like racing";
var regex = /^John/;
var result = regex.test(string);
console.log(result); // true
```

```javascript
var string = "Ricky and John Both like racing";
var regex = /^John/;
var result = regex.test(string);
console.log(result); // false
```

#### 18. Match Ending String Patterns
```javascript
var string = "John loves Emma";
var regex = /Emma$/;
var result = regex.test(string);
console.log(result); // true
```

```javascript
var string = "Emma loves John";
var regex = /Emma$/;
var result = regex.test(string);
console.log(result); // false
```

#### 19. Match All Letters and Numbers
```javascript
var string = "There are 5 crates.";
var regex = /\w/g;
var result = string.match(regex).length;
console.log(result); // 15
```

```javascript
var string = "Thereare5crates";
var regex = /\w/g;
var result = string.match(regex).length;
console.log(result); // 15
```

#### 20. Match Everything But Letters and Numbers
```javascript
var string = "There are 5 crates.";
var regex = /\W/g;
var result = string.match(regex);
console.log(result); // [" ", " ", " ", "."]
```

```javascript
var string = "Thereare5crates";
var regex = /\W/g;
var result = string.match(regex);
console.log(result); // null
```

#### 21. Match All Numbers
```javascript
var string = "Your burger will be $5.00";
var regex = /\d/g;
var result = string.match(regex);
console.log(result); // ["5", "0", "0"]
```

#### 22. Match All Non-Numbers
```javascript
var string = "Your burger will be $5.00";
var regex = /\D/g;
var result = string.match(regex);
console.log(result); // ["Y", "o", "u", "r", " ", "b", "u", "r", "g", "e", "r", " ", "w", "i", "l", "l", " ", "b", "e", " ", "$", "."]
```

#### 23. Restrict Possible Usernames
> ###### requirements
> 1. If there are numbers, they must be at the end.
> 2. Letters can be lowercase and uppercase
> 3. At least two letters long.

```javascript
var string = "Jack1";
var regex = /^[A-Za-z]{2,}\d*$/;
var result = regex.test(string);
console.log(result); // true
```

```javascript
var string = "Jack";
var regex = /^[A-Za-z]{2,}\d*$/;
var result = regex.test(string);
console.log(result); // true
```

```javascript
var string = "jo1";
var regex = /^[A-Za-z]{2,}\d*$/;
var result = regex.test(string);
console.log(result); // true
```

```javascript
var string = "j2123";
var regex = /^[A-Za-z]{2,}\d*$/;
var result = regex.test(string);
console.log(result); // false
```

```javascript
var string = "ja23ck1";
var regex = /^[A-Za-z]{2,}\d*$/;
var result = regex.test(string);
console.log(result); // false
```

#### 24. Match Whitespace
```javascript
var string = "Whitespace is important.";
var regex = / /g;
var result = string.match(regex);
console.log(result); // [" ", " "]
```

```javascript
var string = "Whitespace is important.";
var regex = /\s/g;
var result = string.match(regex);
console.log(result); // [" ", " "]
```

#### 25. Match Non-Whitespace Characters
```javascript
var string = "s p a c e";
var regex = /[^ ]/g;
var result = string.match(regex);
console.log(result); // ["s", "p", "a", "c", "e"]
```

```javascript
var string = "s p a c e";
var regex = /\S/g;
var result = string.match(regex);
console.log(result); // ["s", "p", "a", "c", "e"]
```

#### 26. Specify Upper and Lower Number of Matches
```javascript
var string = "Ohhh no";
var regex = /Oh{3,6} no/;
var result = regex.test(string);
console.log(result); //true
```

```javascript
var string = "Ohhh no";
var regex = /Oh{3,} no/;
var result = regex.test(string);
console.log(result); // true
```

```javascript
var string = "Ohhh no";
var regex = /Oh{4,6} no/;
var result = regex.test(string);
console.log(result); // false
```

#### 27. Specify Only the Lower Number of Matches
```javascript
var string = "Hazzzzah";
var regex = /z{4,}/;
var result = regex.test(string);
console.log(result); // true
```

#### 28. Specify Exact Number of Matches
```javascript
var string = "Timmmmber";
var regex = /Tim{4}ber/;
var result = regex.test(string);
console.log(result); // true
```

#### 29. Check for All or None
```javascript
var string = "favorite";
var regex = /favou?rite/;
var result = regex.test(string);
console.log(result); // true
```

```javascript
var string = "favourite";
var regex = /favou?rite/;
var result = regex.test(string);
console.log(result); // true
```

#### 30. Positive Lookahead
```javascript
var string = "fatihturgut1";
var regex = /fatihturgut(?=1)/;
var result = string.match(regex);
console.log(result); // ["fatihturgut", index: 0, input: "fatihturgut1", groups: undefined]
```

```javascript
var string = "fatihturgut2";
var regex = /fatihturgut(?=1)/;
var result = string.match(regex);
console.log(result); // null
```

#### 31. Negative Lookahead
```javascript
var string = "fatihturgut1";
var regex = /fatihturgut(?!2)/;
var result = string.match(regex);
console.log(result); // ["fatihturgut", index: 0, input: "fatihturgut1", groups: undefined]
```

```javascript
var string = "fatihturgut1";
var regex = /fatihturgut(?!1)/;
var result = string.match(regex);
console.log(result); // null
```

#### 32. Use Capture Groups to Search and Replace
```javascript
var string = "The sky is silver.";
var regex = /silver/;
var result = string.replace(regex, "blue");
console.log(result); // The sky is blue.
```

```javascript
var string = "Code Camp";
var regex = /(\w+)\s(w+)/;
var result = string.replace(regex, "$1 $2");
console.log(result); // Code Camp.
```

```javascript
var string = "This sandwich is good.";
var regex = /good/;
var result = string.replace(regex, "okey-dokey");
console.log(result);
```

#### 33. Remove Whitespace from Start and End
```javascript
var string = "    Hello World!    ";
var regex = /^\s+|\s+$/g;
var result = string.replace(regex, "");
console.log(result); // Hello World!
```

## License

This project is licensed under the GNU General Public License v2.0 - see the [LICENSE](LICENSE) file for details
