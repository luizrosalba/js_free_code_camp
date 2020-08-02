## Expressões regulares 
https://regexr.com/
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
Negando caracteres (^dentro de parenteses) 
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
Regular Expressions: Find Characters with Lazy Matching
Lazy and Greedy matches : 
Regular expressions are by default greedy
Lazy (?)-> encontra a menor match de um regex 
Greedy (default) -> encontra a maior match de um regex 

regex: /t[a-z]*i/ 
string "titanic". 

This regex is basically a pattern that starts with t, ends with i, and has some letters in between.
"titanic" matched greedy /t[a-z]*i/ return ["titani"] It finds the largest sub-string possible to fit the pattern.
"titanic" matched lazy  /t[a-z]*?i/ returns ["ti"].It finds the smallest sub-string possible to fit the pattern.

Note
Parsing HTML with regular expressions should be avoided, but pattern matching an HTML string with regular expressions is completely fine.


```Javascript

let text = "<h1>Winter is coming</h1>";
let myRegex = /<h.*?>/; // retorna um vetor com <h.> dentro dele  
let result = text.match(myRegex);

```
sem os colchetes, o operador ^ procura pela ocorrencia de um padrão no começo de uma string  
```Javascript
let rickyAndCal = "Cal and Ricky both like racing.";
let calRegex = /^Cal/; // Change this line
let result = calRegex.test(rickyAndCal);
```
o operador $ procura pela ocorrencia no final de uma string 

```Javascript
let caboose = "The last car on a train is the caboose";
let lastRegex = /caboose$/; // Change this line
let result = lastRegex.test(caboose);

```
Regular Expressions: Match All Letters and Numbers
/\w/ é um atalho para uma regex que busca todas as letras e numeros (e tambem o underscore _ )  sem considerar o case sensitive 
```Javascript
let longHand = /[A-Za-z0-9_]+/;
let shortHand = /\w+/;
let numbers = "42";
let varNames = "important_var";
longHand.test(numbers); // Returns true
shortHand.test(numbers); // Returns true
longHand.test(varNames); // Returns true
shortHand.test(varNames); // Returns true

```
Verificando as condições . Se uma entrada é verdadeira , o teste deve retornar verdadeira. Se nao encontra a opção retorna falsa . 
1) Usernames can only use alpha-numeric characters.
2) The only numbers in the username have to be at the end. There can be zero or more of them at the end. Username cannot start with the number.
3) Username letters can be lowercase and uppercase.
4) Usernames have to be at least two characters long. A two-character username can only use alphabet letters as characters.

```Javascript
let username = "l00";
// ^[a-z] começa com uma letra 
//[0-9][0-9]+ - ou termina com dois ou mais numeros 
// | aplica mais uma condição 
// [a-z]+ -ou has one or more letters next
// \d* - termina com zero ou mais numeros no final 
///$ - final da entrada 
let userCheck = /^[a-z]([0-9][0-9]+|[a-z]+\d*)$/i;
let result = userCheck.test(username);
console.log(result);
```
Regular Expressions: Match Whitespace
Busca por espaço, enter, tab,  form feed, e nova linha   \s 
[ \r\t\f\n\v]

```Javascript
let whiteSpace = "Whitespace. Whitespace everywhere!"
let spaceRegex = /\s/g;
whiteSpace.match(spaceRegex);
// Returns [" ", " "]
```
Busca por nao whitespace 

```Javascript
let whiteSpace = "Whitespace. Whitespace everywhere!"
let nonSpaceRegex = /\S/g;
whiteSpace.match(nonSpaceRegex).length; // Returns 32
```
Regular Expressions: Specify Upper and Lower Number of Matches
Buscar por um determinado numero de matches 

```Javascript
let A4 = "aaaah";
let A2 = "aah";
let multipleA = /a{3,5}h/; /// busca por a aparecendo entre 3 a 5 vezes na string
multipleA.test(A4); // Returns true
multipleA.test(A2); // Returns false
```
egular Expressions: Specify Only the Lower Number of Matches
```Javascript
let A4 = "haaaah";
let A2 = "haah";
let A100 = "h" + "a".repeat(100) + "h";
let multipleA = /ha{3,}h/;
multipleA.test(A4); // Returns true
multipleA.test(A2); // Returns false
multipleA.test(A100); // Returns true
```
Regular Expressions: Check for All or None
? Retorna true para 0 ou uma ocorrencia do caractere anterior
```Javascript
let american = "color";
let british = "colour";
let rainbowRegex= /colou?r/;
rainbowRegex.test(american); // Returns true
rainbowRegex.test(british); // Returns true
```
Regular Expressions: Positive and Negative Lookahead
positive lookahead will look to make sure the element in the search pattern is there, but won't actually match it.  A positive lookahead is used as (?=...) where the ... is the required part that is not matched.

a negative lookahead will look to make sure the element in the search pattern is not there.  A negative lookahead is used as (?!...) where the ... is the pattern that you do not want to be there. The rest of the pattern is returned if the negative lookahead part is not present.

Uso com match : 
Positive lookahead retorna o prefixo quando ocorre o valor buscado (?=) 
Negative lookahead retorna o prefixo quando não ocorre o valor buscado (?=)
```Javascript
let quit = "qu";
let noquit = "qt";
let quRegex= /q(?=u)/; /// busca q seguido de u sem retornar o u 
let qRegex = /q(?!u)/; /// busca q nao seguido de u sem retornar u 
quit.match(quRegex); // Returns ["q"]
noquit.match(qRegex); // Returns ["q"]
```
Uso com Test 
outro exemplo de lookahead 
Retorna quando ocorre entre 3 a 6 caracteres  \w{3,6}
com pelo menos um digito  \d
incluindo letras e caracteres especiais \D*
```Javascript
let password = "abc123";
let checkPass = /(?=\w{3,6})(?=\D*\d)/;
checkPass.test(password); // Returns true
```
Comeca com nao digito, tem cinco de comprimento e tem dois digitos seguidos
```Javascript
let sampleWord = "bana12";
let pwRegex = /^(?=\D)(\w{2,})(?=\d{2,})/ // Change this line
let result = pwRegex.test(sampleWord);

```

Regular Expressions: Check For Mixed Grouping of Characters
```Javascript
let testStr = "Pumpkin";
let testRegex = /P(engu|umpk)in/;
testRegex.test(testStr);
// Returns true
```
Ignorando palavra no meio 

```Javascript
let myString = "Franklin D. Roosevelt";
let myRegex = /(?=.*Franklin|Eleanor)(?=.*Roosevelt).*/; // Change this line
let result = myRegex.test(myString); // Change this line
// After passing the challenge experiment with myString and see how the grouping works
```

```
```Javascript

```
```Javascript

```
```
```Javascript

```
```Javascript

```

```
```Javascript

```
```Javascript

```

```
```Javascript

```
```Javascript

```

