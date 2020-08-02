## Expressões regulares 
Regular Expressions: Using the Test MethodPassed
Verificando se existe a string myregex dentro da string mystring 
Atenção ! é case sensitive 
```Javascript
let testStr = "freeCodeCamp";
let testRegex = /Code/;
testRegex.test(testStr);
// Returns true
```
Regular Expressions: Match a Literal String with Different Possibilities
Procurando mais de uma palavra com o operador | 
```Javascript
let petString = "James has a pet cat.";
let petRegex = /dog|cat|bird/; // Change this line
let result = petRegex.test(petString);

```
Regular Expressions: Ignore Case While Matching
Ignorando case sensitive 
```Javascript
let myString = "freeCodeCamp";
let fccRegex = /freecodecamp/i; // Change this line
let result = fccRegex.test(myString);

```
Regular Expressions: Extract Matches
usando o match para verificar uma string por uma expressão regular (regex) 
```Javascript
"Hello, World!".match(/Hello/);
// Returns ["Hello"]
let ourStr = "Regular expressions";
let ourRegex = /expressions/;
ourStr.match(ourRegex);
// Returns ["expressions"]

```
Regular Expressions: Find More Than the First Match
Encontrando mais de um caso , retornando um vetor com as ocorrencias encontradas 
ignorando case sensitive 
```Javascript
let repeatRegex = /Repeat/g;
testStr.match(repeatRegex);
// Returns ["Repeat", "Repeat", "Repeat"]
```
Regular Expressions: Match Anything with Wildcard Period
Utilizando coringas 

```Javascript
let humStr = "I'll hum a song";
let hugStr = "Bear hug";
let huRegex = /hu./;
huRegex.test(humStr); // Returns true
huRegex.test(hugStr); // Returns true
```
Regular Expressions: Match Single Character with Multiple Possibilities
Restringindo as possibilidades de match 
```Javascript
let bigStr = "big";
let bagStr = "bag";
let bugStr = "bug";
let bogStr = "bog";
let bgRegex = /b[aiu]g/;
bigStr.match(bgRegex); // Returns ["big"]
bagStr.match(bgRegex); // Returns ["bag"]
bugStr.match(bgRegex); // Returns ["bug"]
bogStr.match(bgRegex); // Returns null
```
Regular Expressions: Match Letters of the Alphabet
Range de characteres 
```Javascript
let catStr = "cat";
let batStr = "bat";
let matStr = "mat";
let bgRegex = /[a-e]at/;
catStr.match(bgRegex); // Returns ["cat"]
batStr.match(bgRegex); // Returns ["bat"]
matStr.match(bgRegex); // Returns null
```
Regular Expressions: Match Numbers and Letters of the Alphabet
(tambem serve para numeros) 
```Javascript
let jennyStr = "Jenny8675309";
let myRegex = /[a-z0-9]/ig;
// matches all letters and numbers in jennyStr
jennyStr.match(myRegex);
```
Regular Expressions: Match Single Characters Not Specified
Negando caracteres 
For example, /[^aeiou]/gi matches all characters that are not a vowel. 
Note that characters like ., !, [, @, / and white space are matched -
the negated vowel character set only excludes the vowel characters.
```Javascript
let quoteSample = "3 blind mice.";
let myRegex = /[^0-9aeiou]/gi; // Change this line
let result = quoteSample.match(myRegex); // Change this line
console.log(result);
```
Regular Expressions: Match Characters that Occur One or More Times
Retorna quantas vezes um caractere é repetido mais de uma vez 
```Javascript
let difficultSpelling = "Mississippi";
let myRegex = /s+/gi; // Change this line
let result = difficultSpelling.match(myRegex);/// s é repetido duas vezes 

```
Regular Expressions: Match Characters that Occur Zero or More Times
Match que verifica regex que com caracteres que acontecem 0 ou mais de uma vez 
```Javascript
// Only change code below this line
let chewieQuote="Aaaaaaaaaaaaaaaarrrgh!"
let chewieRegex = /Aa*/; // Change this line
// Only change code above this line
let result = chewieQuote.match(chewieRegex);
```

```Javascript

```

```Javascript

```


```Javascript

```
```Javascript

```
```Javascript

```
```Javascript

```

```Javascript

```

