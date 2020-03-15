# Regex Examples
Learn **Regular Expressions**, aka **regex**, by inspecting the various examples.

![Regex](https://github.com/fatihturgut/regex-examples/blob/master/regex.png)

### 1. Using the Regex Test Method
```javascript
var string = "The dog chased the cat";
var regex = /the/
var result = regex.test(string);
console.log(result); // true
```

### 2. Match Literal Strings
```javascript
var string = "Hello World";
var regex = /Hello/
var result = regex.test(string);
console.log(result); // true
```

```javascript
var string = "hello World";
var regex = /Hello/
var result = regex.test(string);
console.log(result); // false
```

### 3. Match a Literal String with Different Possibilities (or operator)
```javascript
var string = "Jhonny has cat and dog.";
var regex = /cat|dog|bird/
var result = regex.test(string);
console.log(result); // true
```

### 4. Ignore Case While Matching
```javascript
var string = "davidBeckham";
var regex = /davidbeckham/i;
var result = regex.test(string);
console.log(result); // true
```

### 5. Extract Matches
```javascript
var string = "Extract the word 'coding' form this string";
var regex = /coding/;
var result = string.match(regex);
console.log(result); // ["coding", index: 18, input: "Extract the word 'coding' form this string 'coding'", groups: undefined]
```

### 6. Find More Than the First Match, Multiple Match (g flag)
```javascript
var string = "Repeat, Repeat, Repeat";
var regex = /Repeat/g;
var result = string.match(regex);
console.log(result); // ["Repeat", "Repeat", "Repeat"]
```

### 7. Find More Than the First Match, Multiple Match (i g flags)
```javascript
var string = "Repeat, repeat, repeat";
var regex = /repeat/ig;
var result = string.match(regex);
console.log(result); // ["Repeat", "repeat", "repeat"]
```

### 8. Match Anything with Wildcard Period
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

### 9. Match Single Character with Multiple Possibilities
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

### 10. Match Letters of the Alphabet
```javascript
var string = "The quick brown fox jumps over the lazy dog.";
var regex = /[a-z]/ig;
var result = string.match(regex);
console.log(result); // ["T", "h", "e", "q", "u", "i", "c", "k", "b", "r", "o", "w", "n", "f", "o", "x", "j", "u", "m", "p", "s", "o", "v", "e", "r", "t", "h", "e", "l", "a", "z", "y", "d", "o", "g"]
```

### 11. Match Numbers and Letters of the Alphabet
```javascript
var string = "Number pi is 3.14159265359.";
var regex = /[2-6h-s]/ig;
var result = string.match(regex);
console.log(result); // ["N", "m", "r", "p", "i", "i", "s", "3", "4", "5", "2", "6", "5", "3", "5"]
```

### 12. Match Single Characters Not Specified
```javascript
var string = "3 blind mice.";
var regex = /[^0-9aeiou]/ig;
var result = string.match(regex);
console.log(result); // [" ", "b", "l", "n", "d", " ", "m", "c", "."]
```
### 13. Match Characters that Occur One or More Times
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

### 14. Match Characters that Occur Zero or More Times
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


### 15. Find Characters with Lazy Matching
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

### 16. Find One or More Criminals in a Hunt
```javascript
var string = "P1P2P3P4P4P5CCCP7P8P9";
var regex = /C+/;
var result = string.match(regex);
console.log(result); // ["CCC", index: 12, input: "P1P2P3P4P4P5CCCP7P8P9", groups: undefined]
```

### 17. Match Beginning String Patterns
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

### 18. Match Ending String Patterns
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

### 19. Match All Letters and Numbers
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

### 20. Match Everything But Letters and Numbers
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

### 21. Match All Numbers
```javascript
var string = "Your burger will be $5.00";
var regex = /\d/g;
var result = string.match(regex);
console.log(result); // ["5", "0", "0"]
```

### 22. Match All Non-Numbers
```javascript
var string = "Your burger will be $5.00";
var regex = /\D/g;
var result = string.match(regex);
console.log(result); // ["Y", "o", "u", "r", " ", "b", "u", "r", "g", "e", "r", " ", "w", "i", "l", "l", " ", "b", "e", " ", "$", "."]
```

### 23. Restrict Possible Usernames
> ##### requirements
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

### 24. Match Whitespace
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

### 25. Match Non-Whitespace Characters
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

### 26. Specify Upper and Lower Number of Matches
```javascript
```

### 27. Specify Only the Lower Number of Matches
```javascript
```

### 28. Specify Exact Number of Matches
```javascript
```

### 29. Check for All or None
```javascript
```

### 30. Positive and Negative Lookahead
```javascript
```

### 31. Reuse Patterns Using Capture Groups
```javascript
```

### 32. Use Capture Groups to Search and Replace
```javascript
```

### 33. Remove Whitespace from Start and End
```javascript
```

