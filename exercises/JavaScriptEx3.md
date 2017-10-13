# JavaScript Exercise 3 -- Event Handling I
		
> Note:: Complete ALL the exercises in this section.


1.	Use the code in ``event.html`` and ``script.js`` to demonstrate simple event handling.

	``event.html``

	```javascript
	<!doctype html>

	<head>
	   <title>JavaScript Events</title>	
	   <script src="script.js"></script>	
	</head>
	<body>
	   <a href="http://www.fcbarcelona.com" onclick="printAlert();">FC Barcelona</a>
	</body>
	</html>

	```	
	
	``script.js``

	```javascript
	function printAlert()
	{
	   alert("you are about to goto the FC Barcelona website");
	}

	```
