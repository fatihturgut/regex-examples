# Regex Examples
Learn regex by inspecting the regex examples.

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
var string1 = "gooooooooal!";
var string2 = "feels good";
var string3 = "over the moont";
var regex = /go*/;
var result1 = string1.match(regex);
var result2 = string2.match(regex);
var result3 = string3.match(regex);
console.log(result1); // ["goooooooo", index: 0, input: "gooooooooal!", groups: undefined]
console.log(result2); // ["goo", index: 6, input: "feels good", groups: undefined]
console.log(result3); // null
```

```javascript
var string = "Aaaaarrghhh!";
var regex = /Aa*/;
var result = string.match(regex);
console.log(result); // ["Aaaaa", index: 0, input: "Aaaaarrghhh!", groups: undefined]
```


### 15. Find Characters with Lazy Matching
```javascript
```

### 16. Find One or More Criminals in a Hunt
```javascript
```

### 17. Match Beginning String Patterns
```javascript
```

### 18. Match Ending String Patterns
```javascript
```

### 19. Match All Letters and Numbers
```javascript
```

### 20. Match Everything But Letters and Numbers
```javascript
```

### 21. Match All Numbers
```javascript
```

### 22. Match All Non-Numbers
```javascript
```

### 23. Restrict Possible Usernames
```javascript
```

### 24. Match Whitespace
```javascript
```

### 25. Match Non-Whitespace Characters
```javascript
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

