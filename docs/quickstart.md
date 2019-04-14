# Primeres passes

A part del `textarea` on vulguem que s'escrigui el resultat, necessitarem un `div` que indicarà on es crearà, dinàmicament, el teclat personalitzat. Necessitarem poder identificar aquest `div` d'alguna manera, per exemple, podem crear el següent `<div id="keyboard"></div>`


Un cop afegit jQuery, cal afegir l'arxiu javascript `keyboardComponent.js` just abans de tancar l'etiqueta `<body>` del l'html:

```html
<body>
	<!-- Altres etiquetes HTML -->
	<textarea id="message" style="width: 100%; height: 100px"></textarea>
	<div id="keyboard"></div>
	<!-- Altres etiquetes HTML -->
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
	<script src="keyboardComponent.js"></script>
</body>
```

Mes avall d'aquest codi, podem inicialitzar un sencill teclat mitjançant el següent codi javascript:

```javascript
var options = {
	input: $("#message"),
	keyboard: {
		lines :[
			["1","2","3"],
			["4","5","6"],
			["7","8","9"]
		]
	}
}
$("#keyboard").createKeyboard(options);
```