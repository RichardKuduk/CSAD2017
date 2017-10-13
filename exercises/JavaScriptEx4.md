# JavaScript Exercise 4 -- Event Handling II
		
> Note:: Complete ALL the exercises in this section.  If you need help email thomas.devine@lit.ie



	
1.	You are meant to keep your content, presentation and behavior separate. 
	Use the Listings ``FirstEventV2.html`` and ``script.js`` in the lecture slides so the HTML content 
	and JavaScript behavior are separated.


	
1.	Use the code ``fruit1.html`` and using JavaScript in a file called ``fruit1.js`` change the colour of all paragraphs to red.  Use the method ``setAttribute("style","color:red");``

	
	``fruit1.html``

	```javascript	
	<html>
	<head>
	<script src="fruit1.js"></script>
	</head>

	<body>
	<h1>Fruit</h1>
	<p>Apples</p>
	<p>Pears</p>
	<p>Oranges</p>
	</body>
	</html>

	```


1.	Add to the code in ``fruit1.html`` a button with the caption *Style*. 
	Only when this button is clicked should the paragraphs be coloured red.
	See [this](http://jsfiddle.net/barcaxi/y7eLdzjp/) fiddle code for a button example.
	

	
1.	Use the code ``fruit2.html`` and using JavaScript in a file called ``fruit2.js`` change the <span> 
	value when a selection is made from the dropdown control.
	See [this fiddle](http://jsfiddle.net/barcaxi/b45g4zt1) code for a similar dropdown example.

	
	``fruit2.html``
	
	```javascript
	<html>
	<head>
	<script src="fruit2.js"></script>
	</head>

	<body>
	<h1>Fruit</h1>
	<select>
	   <option value="Apples">Apples</option>
	   <option value="Pears">Pears</option>
	   <option value="Oranges">Oranges</option>
	</select>
	<br>
	Fruit selected <span>Apples</span>
	<hr>
	</body>
	</html>
	
	```

1.	Update the JavaScript file ``fruit2.js`` to change the colour of the ``<h1>`` heading to blue when 
	the user moves the mouse over it.  And when the mouse leaves the heading the colour should be restored to black.

	See [HTML DOM Events](http://www.w3schools.com/jsref/dom_obj_event.asp)
	
	
1.	Use the code ``toUpper.html`` and using JavaScript in a file called ``toUpper.js`` allow the user 
	to type text in the first textbox and when the *To Upper* button is pressed display the text 
	input using uppercase in the second textbox.
	
	``toUpper.html``

	```javascript
	<html>
	<head>
	<script src="toUpper.js"></script>
	</head>

	<body>
	<h1>To Upper</h1>
	<input type="text">
	<button>To Upper--></button>
	<input type="text">
	<hr>
	</body>
	</html>
	
	```		

	
	See [this fiddle code](http://jsfiddle.net/barcaxi/8b3v1vzc/1/) for a similar textbox example. 
	You'll also need to use the [JavaScript String Reference](http://www.w3schools.com/jsref/jsref_obj_string.asp)


	
1.	Earlier you produced the HTML output for a celsius to fahrenheit table using JavaScript. 
	Modify the code so the same output is achieved, but the JavaScript code is entirely stored 
	in a file ``htmlFunctions.js``. 
	The only HTML code necessary is shown in ``cToFtable.html``
	
	``cToFtable.html``

	```javascript
	<!doctype html>
	<head>		   
	   <script src="htmlFunctions.js"></script>	
	   <title>Celsius to Fahrenheit</title>
	</head>
	<body>
	</body>
	</html>

	```		
	

1.	Using the HTML code in ``favouriteV2.html`` below write the JavaScript code needed in the file 
	``favouriteV2.js`` to update the bold tag with the correct colour when a new colour is selected 
	from the dropdown box.

	You must capture the ``onchange`` event associated with the dropdown box. 

	``favouriteV2.html``

	```javascript
	<html>
	<head>
	<script src="favouriteV2.js"></script>
	<title>My Favourite Colour</title>
	</head>
	<body>
	Choose:
	<SELECT id="colourCombo" name="colour">
	<OPTION value="red">red</option>
	<OPTION value="green">green</option>
	<OPTION value="blue">blue</option>
	</SELECT>

	<hr/>
	<b id="colour">red</b> is my favourite colour.
	</body>
	</html>
	
	```
	
