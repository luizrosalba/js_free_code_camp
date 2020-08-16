## Expressões regulares 
https://regexr.com/

```Javascript
abc…	Letters
123…	Digits
\d	Any Digit
\D	Any Non-digit character
.	Any Character
\.	Period
[abc]	Only a, b, or c
[^abc]	Not a, b, nor c
[a-z]	Characters a to z
[0-9]	Numbers 0 to 9
\w	Any Alphanumeric character
\W	Any Non-alphanumeric character
{m}	m Repetitions
{m,n}	m to n Repetitions
*	Zero or more repetitions
+	One or more repetitions
?	Optional character
\s	Any Whitespace
\S	Any Non-whitespace character
^…$	Starts and ends
(…)	Capture Group
(a(bc))	Capture Sub-group
(.*)	Capture all
(abc|def)	Matches abc or def

```

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


´´´Javascript
+-------------------+-----------------+------------------------------+
| Greedy quantifier | Lazy quantifier |        Description           |
+-------------------+-----------------+------------------------------+
| *                 | *?              | Star Quantifier: 0 or more   |
| +                 | +?              | Plus Quantifier: 1 or more   |
| ?                 | ??              | Optional Quantifier: 0 or 1  |
| {n}               | {n}?            | Quantifier: exactly n        |
| {n,}              | {n,}?           | Quantifier: n or more        |
| {n,m}             | {n,m}?          | Quantifier: between n and m  |
+-------------------+-----------------+------------------------------+
Add a ? to a quantifier to make it ungreedy i.e lazy.
´´´
Example:
test string : stackoverflow
greedy reg expression : s.*o output: stackoverflo
lazy reg expression : s.*?o output: stacko

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
Regular Expressions: Reuse Patterns Using Capture Groups
You can search for repeat substrings using capture groups. Parentheses, ( and ), are used to find repeat substrings. You put the regex of the pattern that will repeat in between the parentheses.

To specify where that repeat string will appear, you use a backslash (\) and then a number. This number starts at 1 and increases with each additional capture group you use. An example would be \1 to match the first group.
Using the .match() method on a string will return an array with the string it matches, along with its capture group.

```Javascript
let repeatStr = "regex regex";
let repeatRegex = /(\w+)\s\1/;
repeatRegex.test(repeatStr); // Returns true
repeatStr.match(repeatRegex); // Returns ["regex regex", "regex"]
```
Aqui ele procura o caractere inicio com um digito ou mais ,procura um espaço , repete o primeiro grupo (mais de um caractere), repete o espaço e procura o caractere de fim . Ele só respondera a essa regex entao 100 100 100 100 nao funciona pois ele nao encontra o caractere de fim e inicio com tres repeticoes entre eles   
```Javascript
let repeatNum = "42 42 42";
let reRegex = /^(\d+)\s\1\2\1$/; // Change this line
let result = reRegex.test(repeatNum);

```
Regular Expressions: Use Capture Groups to Search and Replace

```Javascript
let wrongText = "The sky is silver.";
let silverRegex = /silver/;
wrongText.replace(silverRegex, "blue");
// Returns "The sky is blue."
```
You can also access capture groups in the replacement string with dollar signs ($).
```Javascript
let str = "one two three";
let fixRegex = /(\w+)\s(\w+)\s(\w+)/; // Change this line
let replaceText = "$3 $2 $1"; // Change this line
let result = str.replace(fixRegex, replaceText);
console.log (result);

```
Regular Expressions: Remove Whitespace from Start and End
Seleciona e remove um texto do inicio e final de uma string 

```Javascript
let hello = "   Hello, World!  ";
let wsRegex = /^\s+|\s+$/; // Change this line
let result = hello.replace(wsRegex, ""); // Change this line
console.log (result);

```
