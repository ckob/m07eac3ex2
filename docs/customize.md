# Personalització

Al inicialitzar KeyboardComponent mitjançant el mètode `createKeyboard()` li passem un objecte, on podem configurar els següents paràmetres:

### input

Al parámetre `input` se li ha de passar un objecte de tipus jQuery que representi un `textarea` o similar. Aquest serà el destí de l'acció que realitzem al apretar els botons del teclat.
```javascript
input: $("textarea")
```

### keyboard

Mitjançant el parámetre `keyboard` podem personalitzar el teclat. Hi han els següents sub-parámetres:
#### keyboardName `opcional`

Indica el nom identificatiu del teclat. Desprès podem buscar-lo per l'ID `keyboard_nomEscollit`.
```javascript
keyboardName: "abc"
```

#### lines
El teclat es distribueix amb linies, cada una d'aquestes linies es un array i conté un array de tecles. Es a dir, es un array bi-dimensional.

```javascript
lines:[
	["1","2","3"],
	["4","5","6"],
	["7","8","9"]
]
```

Cada un dels botóns pot especificar, o bé un carácter `UTF-8` que s'escriurà tal qual com a l'exemple anterior, o bé un objecte amb els següents atributs:
 - `customWidth` paràmetre opcional que permet personalitzar el tamany que ocuparà en la linia.
 - `key` caràcter que es visualitza al botó
 - `action` acció que es realitza al pulsar el botó. És una funció que té un parámetre que es el text que estem editant i que retorna el resultat desitjat. Al següent exemple, s'escriu un espai la final del text.

```javascript
{
	key: "__",
	action: s => s + " "
}
```
Així doncs, per exemple, podriem ampliar el teclat de l'exemple anterior afegint un espai i una tecla de borrar última linia:
```javascript
lines:[
	["1","2","3"],
	["4","5","6"],
	["7","8","9"],
	[{
		key: "__",
		action: s => s + " "
	},{
		key: "◀️",
		action: s => s.slice(0,-1)
	}]
]
```
