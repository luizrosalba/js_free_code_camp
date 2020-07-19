# js_free_code_camp
meus testes do free code camp 
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

Nested arrays 
var myArray = [[],[]];

// Setup
var myArray = [[1,2,3], [4,5,6], [7,8,9], [[10,11,12], 13, 14]];
// Retorna 8 
var myData = myArray[2][1];

//vetor 
var removedFromMyArray=array.push();  /// adiciona ultima pos
var removedFromMyArray=array.pop();  /// remove ultimo pos
var removedFromMyArray=array.shift(); // remove primeiro pos
myArray.unshift(["Paul",35]); /// adiciona na primeira posicao

Variables which are used without the var keyword are automatically created in the global scope.(mesmo dentro de funções)
var dentro de função cria uma variavel com escopo local
It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

se uma função nao retorna nada , seu retorno é undefined. 
=== compara valor e tipo 


### /// switch case faz === nas comparações 
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


### Retornando undefined
function retornaUndefined (){
return ; 
}


### objects 
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


### deleta propriedade make do objeto anotherObject
delete anotherObject.make; 

However, if your object has any non-string properties, JavaScript will automatically typecast them as strings.

There are two ways to access the properties of an object: dot notation (.) and bracket notation ([]), similar to an array.

Dot notation is what you use when you know the name of the property (nome conhecido) you're trying to access ahead of time.

Se a prop nao existe e vc quer criar use a notação ponto e inicialize (se nao inicializar nao vai criar )

If the property of the object you are trying to access has a space in its name (ou é uma variavel que já existe) , you will need to use bracket notation.
Se ela já existe ou é uma variável , use bracket sem aspas 
criar com aspas fará ela criar uma prop com  o nome da variável e nao com o conteúdo da variável . 

### We can use the .hasOwnProperty(propname) method of objects to determine if that object has the given property name. .hasOwnProperty() returns true or false if the property is found or not.

Example

var myObj = {
  top: "hat",
  bottom: "pants"
};
myObj.hasOwnProperty("top");    // true
myObj.hasOwnProperty("middle"); // false


JavaScript Object Notation or JSON is a related data interchange format used to store data.

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


/// desafio da musica 


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
