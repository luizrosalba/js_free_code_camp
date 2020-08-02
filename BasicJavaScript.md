# Basic JavaScript
Cursando o Javascript algorithms and data Structues certification 
## Basics 

JavaScript provides eight different data types which are undefined, null, boolean, string, symbol, bigint, number, and object.
In camelCase, multi-word variable names have the first word in lowercase and the first letter of each subsequent word is capitalized.
Unlike some other programming languages, single and double quotes work the same in JavaScript.

Code	Output
\'	single quote
\"	double quote
\\	backslash
\n	newline
\r	carriage return
\t	tab
\b	word boundary
\f	form feed

when the + operator is used with a String value, it is called the concatenation operator. 

## Criando arrays 



const arr = [1,2,3]; 
ou

const arr = new Array(1,2,3); 

ou 

const persons = Array.of('Luiz', 'Dani")  ; 
ou 
const numerosEPessoas = Array.of('Luiz', 1)  ; 
ou 
const numerosEPessoas = Array(3)  ;  /// cria uma array com 3 pos vazias 
ou 
const numerosEPessoas = Array(3,1)  ;  /// cria um array com 3 e 1 

Array.from(origem) /// cria uma nova instancia de array a partir de um parâmetro array-like ou iterable object


const divArray = Array.from (divs)  /// cria um array a partir do objeto div (que no exemplo do curso era um NodeList). A partir daí pode-se utilizar funções de array como pop , shift , etc  

## Nested arrays 

Site bom com documentação 

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/fill

var myArray = [[],[]];

// Setup
var myArray = [[1,2,3], [4,5,6], [7,8,9], [[10,11,12], 13, 14]];
var myData = myArray[2][1];// Retorna 8 

## Inicializando 
O método fill é um método mutável, ele irá mudar o objeto em si, e retorná-lo, não somente uma cópia do objeto.
```Javascript
arr.fill(valor[, ínicio = 0[, fim = this.length]]) 
[1, 2, 3].fill(4);               // [4, 4, 4]   preenche com 4 tudo 
[1, 2, 3].fill(4, 1);            // [1, 4, 4]   preenche com 4 a partir da posicao 1 
[1, 2, 3].fill(4, 1, 2);         // [1, 4, 3]   preenche com 4 a partir da posicao 1 até 2 
Array(3).fill(4);                // [4, 4, 4]   preenche um vetor de tres posições com 4 
[].fill.call({ length: 3 }, 4);  // {0: 4, 1: 4, 2: 4, length: 3}
```


## Alterando vetores (arrays)
```Javascript
var removedFromMyArray=array.push();  /// adiciona ultima pos
var removedFromMyArray=array.pop();  /// remove ultimo pos
var removedFromMyArray=array.shift(); // remove primeiro pos e retorna o elemento removido 
const tamanho  = myArray.unshift(["Paul",35]); /// adiciona na primeira posicao ao ser aplicado, retorna o tamanho do array  
const alimentos = frutas.concat(salgados) ; // faz um merge concatenando em alimentos o array salgados e frutas 
```




## Iterando vetores (arrays)
```Javascript
const arr = [1,2,3,4,5];  
arr.forEach((value,index) => {console.log(`${index}:${value}`)});

frutas.forEach((fruta,index,arr) => console.log(index,fruta,arr));

```

### Iterando todos os elementos de um array 
```Javascript
function multiplyAll(arr) {
  var product = 1;
  // Only change code below this line
  for (var i=0; i < arr.length; i++) {
   for (var j=0; j < arr[i].length; j++) {
      product*=arr[i][j];
  }
}
  // Only change code above this line
  return product;
}

multiplyAll([[1,2],[3,4],[5,6,7]]);
```


## Métodos de Arrays

### slice :  
Imutável Fatia o array 
```Javascript
const arr = [1,2,3,4,5];  
Arr.slice(0,2); // [1,2]
Arr.slice(2); // [3,4,5]
Arr.slice(-1); // [5]
Arr.slice(-3); // [3,4,5]
```



### splice : 

Não é imutavel, Altera o array adicionando novos elementos enquanto remove elementos antigos 
```Javascript
const arr = [1,2,3,4,5];  
Arr.splice(2); // remove a partir da posicao 2 [3,4,5] 
console.log(arr); /// [1,2]
Arr.splice(0,0,'first'); // [] /// inicio, quanto itens remove o que adicionar a partir da primeira posicao 
console.log(arr); /// ["fisrt",1,2]; 

```


## map  
Retorna um novo array de mesmo tamanho iterando cada item de um array 
```Javascript
const arr = [1,2,3,4,5];  
arr.map (value => value *2); // retorna um novo array [2,4,6,8,10]

```

## flat  
Retorna um novo array com todos os elementos de um sub-array concatenados de forma recursiva de acordo com a profundidade especificada (depth) 
```Javascript
const arr = [1,2,[3,4]];  
arr.flat(); // retorna um novo array com profundidade 1 [1,2,3,4]
arr.flat(2); // retorna um novo array com profundidade 2 , neste caso não terá diferenca mas se houvessem outros arrays dentro de arr só iria até a segunda camanda de arr 

```

## flatMap  
 Retorna um novo array assim como faz a função map e executa um flat de profundidade 1 

```Javascript
const arr = [1,2,3,4];  
arr.flatMap (value => [value *2]); // retorna um novo array [2,4,6,8]
arr.flatMap (value => [[value *2]]); // retorna um novo array [[2],[4],[6],[8]]
```


## keys  
retorna um array iterator que contem as chaves para cada elemento do array 
```Javascript
const arr = [1,2,3,4];  
const arrIterator = arr.keys();
arrIterator.next(); {value:0,done:false};
arrIterator.next(); {value:1,done:false};
arrIterator.next(); {value:2,done:false};
arrIterator.next(); {value:3,done:true};
```


## values : 
retorna um array iterator que contém os valores para cada elemento do array 
```Javascript
const arr = [1,2,3,4];  
const arrIterator = arr.values();
arrIterator.next(); {value:1,done:false};
arrIterator.next(); {value:2,done:false};
arrIterator.next(); {value:3,done:false};
arrIterator.next(); {value:4,done:true};
```


## entries : 
retorna um par chave valor para cada elemento do array 
```Javascript
const arr = [1,2,3,4];  
const arrIterator = arr.values();
arrIterator.next(); {value:[0,1],done:false};
arrIterator.next(); {value:[1,2],done:false};
arrIterator.next(); {value:[2,3],done:false};
arrIterator.next(); {value:[3,4],done:true};
```



## Buscar elementos 

## find 
Retorna o primeiro item de um array que satisfaz uma condição 
```Javascript
const arr = [1,2,3,4];  
const firstGreatherThanTwo = arr.find (value => value > 2) ; /// 3 

```

## findIndex 
Retorna o indice do primeiro item de um array que satisfaz uma condição 
```Javascript
const arr = [1,2,3,4];  
const firstGreatherThanTwo = arr.findIndex (value => value > 2) ; /// 2
```



## filter
 Retorna um array com todos os elementos que satisfazem uma condição 
```Javascript
const arr = [1,2,3,4];  
const allValuesGreatherThanTwo = arr.filter (value => value > 2) ; /// [3,4]

```

## indexOf 
Retorna o primeiro índice em que um elemento pode ser encontrado em um array 
```Javascript
const arr = [1,3,3,4,3];  
const firstIndexOfItem = arr.indexOf(3); /// 1

```

## lastIndexOf 
Retorna o ultimo índice em que um elemento pode ser encontrado em um array 
```Javascript

const arr = [1,3,3,4,3];  
const firstIndexOfItem = arr.indexOf(3); /// 4
```

## includes 
Retorna um booleano verificando se determinado elemento existe no array 
```Javascript
const arr = [1,3,3,4,3];  
const hasItemOne = arr.includes(1); /// true 
const hasItemTwo = arr.includes(2); /// false 

```


## some 
Retorna um booleano verificando se pelo menos um item de um array satisfaz a condição 
```Javascript
const arr = [1,3,3,4,3];  
const hasSomeEvenNumber = arr.some (value => value % 2 ===0 ) ; /// true
```



## some 
Retorna um booleano verificando se todos os itens de um array satisfazem uma condição 
```Javascript
const arr = [1,3,3,4,3];  
const allEvenNumbers = arr.every (value => value % 2 ===0 ) ; /// false
```


## some 
Retorna um booleano verificando se todos os itens de um array satisfazem uma condição 
```Javascript
const arr = [1,3,3,4,3];  
const allEvenNumbers = arr.every (value => value % 2 ===0 ) ; /// false
```

## sort 
ordenacao de acordo com condição 
```Javascript
students.sort((current,next) => current.grade - next.grade) /// ordena do menor pro maior 
students.sort((current,next) => next.grade - current.grade) /// ordena do maior pro menor 
```

## reverse 
inverte o array 
```Javascript
const arr = [1,2,3,4,5];  
arr.reverse(); /// [5 , 4 , 3 , 2 , 1]
```

## join 
transformando um array em outro tipo de dados 
join junta todos os elementos de um array separados por um delimitar e retorna uma string 
```Javascript
const arr = [1,2,3,4,5];  
arr.join('-'); /// "1-2-3-4-5"
```

## reduce
Retorna um novo tipo de dado iterando cada posicao de um array 
```Javascript
const arr = [1,2,3,4,5];  
arr.reduce ((total,value)=> total+= value, 0); /// para cada item executa afuncao o primeiro arg eh o retorno comeca com um inteiro com valor 0 
```



## Escopo 

Variables which are used without the var keyword are automatically created in the global scope.(mesmo dentro de funções)
var dentro de função cria uma variavel com escopo local
It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

## Undefined 
se uma função nao retorna nada , seu retorno é undefined. 
=== compara valor e tipo 


### /// switch case faz === nas comparações 
```Javascript
function switchOfStuff(val) {
  var answer = "";
  // Only change code below this line
  switch (val){
    case "a":
    answer="apple";
    break;
    case "b":
    answer="bird";
    break;
    case "c":
    answer="cat";
    break;
    default:
    answer="stuff";
    break;
  }
  // Only change code above this line
  return answer;
}

switchOfStuff(1);


```
### Retornando undefined
```Javascript
function retornaUndefined (){
return ; 
}

```

### objects 
```Javascript
var cat = {
  "name": "Whiskers",
  "legs": 4,
  "tails": 1,
  "enemies": ["Water", "Dogs"]
};

var anotherObject = {
  make: "Ford",
  5: "five",
  "model": "focus"
};

```

### delete

propriedade make do objeto anotherObject

delete anotherObject.make; 

However, if your object has any non-string properties, JavaScript will automatically typecast them as strings.

There are two ways to access the properties of an object: dot notation (.) and bracket notation ([]), similar to an array.

Dot notation is what you use when you know the name of the property (nome conhecido) you're trying to access ahead of time.

Se a prop nao existe e vc quer criar use a notação ponto e inicialize (se nao inicializar nao vai criar )
para acessar o valor use [][]

If the property of the object you are trying to access has a space in its name (ou é uma variavel que já existe) , you will need to use bracket notation.
Se ela já existe ou é uma variável , use bracket sem aspas 
criar com aspas fará ela criar uma prop com  o nome da variável e nao com o conteúdo da variável . 

### .hasOwnProperty()
We can use the .hasOwnProperty(propname) method of objects to determine if that object has the given property name. .hasOwnProperty() returns true or false if the property is found or not.

Example
```Javascript
var myObj = {
  top: "hat",
  bottom: "pants"
};
myObj.hasOwnProperty("top");    // true
myObj.hasOwnProperty("middle"); // false

```

JavaScript Object Notation or JSON is a related data interchange format used to store data.
```Javascript
// Setup
var myStorage = {
  "car": {
    "inside": {
      "glove box": "maps",
      "passenger seat": "crumbs"
     },
    "outside": {
      "trunk": "jack"
    }
  }
};

var gloveBoxContents = myStorage.car.inside["glove box"]; // acessando glove box 

```

### /// desafio da musica 

```javascript

// Setup
var collection = {
  2548: {
    album: "Slippery When Wet",
    artist: "Bon Jovi",
    tracks: [
      "Let It Rock",
      "You Give Love a Bad Name"
    ]
  },
  2468: {
    album: "1999",
    artist: "Prince",
    tracks: [
      "1999",
      "Little Red Corvette"
    ]
  },
  1245: {
    artist: "Robert Palmer",
    tracks: [ ]
  },
  5439: {
    album: "ABBA Gold"
  }
};

// Only change code below this line
function updateRecords(id, prop, value) {
  
  if (value=="" && collection[id].hasOwnProperty(prop))  /// se value for vazio delete e tiver a prop 
    delete collection[id][prop]; /// remove a prop 

  if (prop!="tracks" && value!="")  /// se prop nao for track e value nao estiver vazia 
  {
      collection[id][prop]=value; 
  }
  if (prop=="tracks" && value!="")  /// se prop for tracks e value nao estiver vazia 
  {
    if (!collection[id].hasOwnProperty(prop)) /// se nao tem tracks 
    collection[id][prop]=[value]; /// cria e inicializa 
    else /// se jah tem tracks 
    collection[id][prop].push(value); /// pusha value para o  final de tracks 
  }
  return collection;
}

//updateRecords(5439, "tracks", "Take a Chance on Me")
//updateRecords(2548, "tracks", "")
console.log (collection);
```


### gerar numero entre dois intervalos excluindo o max  
```Javascript
function randomRange(myMin, myMax) {
  // Only change code below this line
  
  return Math.floor(Math.random() * (myMax - myMin + 1)) + myMin;
  
  // Only change code above this line
}
```



### parseInt ,
Em outras bases The parseInt() function parses a string and returns an integer. It takes a second argument for the radix, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.
```Javascript
function convertToInteger(str,radix) {
  return parseInt(str,radix);
}
convertToInteger("10011",2); /// converte a string para um inteiro na base binaria 


```

###  a função recursiva 

primeiro a função recursiva vai até a ultima opção e depois outras funções são ativadas exemplo : 

```Javascript
function countup(n) {
  if (n < 1) {
    return [];
  } else {
    const countArray = countup(n - 1);
    countArray.push(n);
    return countArray;
  }
}
console.log(countup(5)); // [ 1, 2, 3, 4, 5 ]
```


At first, this seems counterintuitive since the value of n decreases, but the values in the final array are increasing. This happens because the push happens last, after the recursive call has returned. At the point where n is pushed into the array, countup(n - 1) has already been evaluated and returned [1, 2, ..., n - 1].
```Javascript
/// preenche recursivamente de startNum até end Num 
function rangeOfNumbers(startNum, endNum) {
  if (startNum === endNum) return [startNum];
    const arr = rangeOfNumbers(startNum+1,endNum);
    arr.unshift(startNum);
    return arr;
};
```



