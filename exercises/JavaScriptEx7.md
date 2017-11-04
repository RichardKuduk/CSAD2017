# JavaScript Exercise 7 -- Timers & All!
		
> Note:: Complete ALL the exercises in this section.


1.	Create the HTML file ``SimpleTimer.html`` (below) and JavaScript file ``SimpleTimer.js`` (below) that implements a simple timer.

	``--SimpleTimer.html--``

	```java
	<html>
	<head>
	   <title>
	   </title>    
	   <script type="text/javascript" src="simpleTimer.js"></script>  
	</head>

	<body>

	<form>
	   <input id="start" type="button" value="start" />
	   <input id="stop" type="button" value="stop" />
	</form>
	</body>

	</html>
	
	```

	``--SimpleTimer.js--``

	```java
	window.onload = function() {
	  initFunction();
	}
	 
	var count=0;
	var handle;
	 
	function initFunction() 
	{
	  var startButton = document.getElementById("start");   
	  startButton.onclick=function(){
	    handle=setInterval(addLi,1000);
	  }
	  var stopButton = document.getElementById("stop");   
	  stopButton.onclick=function(){
	    clearInterval(handle);
	  }  
	}
	 
	function addLi()
	{
	  var liElement = document.createElement("li");           
	  count=count+1;
	  var text = document.createTextNode("Item " + count);        
	  liElement.appendChild(text);        
	  var list = document.getElementById("list");
	  list.appendChild(liElement);    
	}
		
	```	
		
1.	The JavaScript code below gets the current time ``t`` from the ``Date`` object in the format HH:MM:SS (e.g. 2:30:00 PM)

	```java
	var d = new Date();
	var t = d.toLocaleTimeString(); // t is the current time

	```

	Create the HTML ``clock.html`` and JavaScript ``clock.js`` files to implement a simple digital clock that shows the current time. 
	It should update every second.

	
1.	Create the HTML and JavaScript files shown below. This code illustrates most of the feature of JavaScript examined so far, and some new features.

	``--CountDown.html--``
	```java
	<!doctype html>
	<head>
	  <title>Countdown</title>
	  <script type="text/javascript" src="countDown.js"></script>
		
	  <style type="text/css">
		body {
		  font-family: sans-serif;
		  color: #333;
		}
		#container {
		  width: 400px;
		  margin: auto;
		}
		h1 { font-size: 5em; }
	  </style>
	</head>

	<body>
	<div id="container">
	  <div id="inputArea">
	  </div>

	  <h1 id="time">0:00</h1>
	  
	  <div id="pauseArea">
	  </div>
	</div> 
	  
	</body>
	</html>
	
	```
		
	``--CountDown.js--``
	
	```java
	// two global variables
	var secondsRemaining;
	var intervalHandle;

	// as soon as the page is loaded...
	window.onload =  function () {
	  initFunction();
	}
	 
	function initFunction()
	{
	  // create input text box and give it an id of "minutes"
	  var inputMinutes = document.createElement("input");
	  inputMinutes.setAttribute("id", "minutes");
	  inputMinutes.setAttribute("type", "text");
	   
	  // create a button
	  var startButton = document.createElement("input");
	  startButton.setAttribute("type", "button");
	  startButton.setAttribute("value", "Start Countdown");
	  startButton.onclick = function () {
	    startCountdown();
	  };
	   
	  // add to the DOM, to the div called "inputArea"
	  document.getElementById("inputArea").appendChild(inputMinutes);
	  document.getElementById("inputArea").appendChild(startButton);
	}
	 
	function startCountdown()
	{
	  // get contents of the "minutes" text box
	  var minutes = document.getElementById("minutes").value;
	  // check if not a number
	  if (isNaN(minutes)) {
	    alert("Please enter a number!");
	    return;
	  }
	  // how many seconds?
	  secondsRemaining =  minutes * 60;
	  // every second, call the tick function
	  intervalHandle = setInterval(tick, 1000);
	  // hide the form
	  document.getElementById("inputArea").style.display = "none";
	}
	 
	function tick()
	{
	  // get the h1
	  var timeDisplay = document.getElementById("time");
	   
	  // turn seconds into mm:ss
	  var min = Math.floor(secondsRemaining / 60);
	  var sec = secondsRemaining - (min * 60);
	   
	  // add a leading zero (as a string value) if seconds less than 10
	  if (sec < 10) {
	    sec = "0" + sec;
	  }
	  // concatenate with colon
	  var message = min + ":" + sec;
	  // now change the display
	  timeDisplay.innerHTML = message;
	   
	  // stop if down to zero
	  if (secondsRemaining === 0) {
	    alert("Done!");
	    clearInterval(intervalHandle);
	    resetPage();
	  }
	  // subtract from seconds remaining
	  secondsRemaining--;
	}
	 
	function resetPage()
	{
	  document.getElementById("inputArea").style.display = "block";
	}
	
	```
	
	Test everything works.
	
	Take time to read and understand what is going on.


1.	Make the following modifications to the code:

	(a) Modify the code so the minimum value allowed is 1 and the maximum is 10.
	
	(b) When the countdown seconds reaches 10 seconds, the remaining seconds should be displayed using the colour red.
	
	(c) Add a *Pause* button so the countdown can be paused when this button is pressed. When the *Pause* button is pressed change the caption of the button to *Restart*. 
	
	(d) When the *Restart* button is pressed the countdown should resume and the button caption should become *Pause* again. 

	Only have the *Pause* button appear when the countdown begins, and when the countdown reaches 0 (ZERO) this button should disappear.

	
1.	You must implement a simple digital clock as shown below that can display the time in three cities in different timezones. 
	
	![alt text](../images/clock.png "Clock")

	When the page ``worldClock.html`` is initially displayed it will show the current time in London (GMT) and update the time every second.
	
	``--worldClock.html--``
	```java
	<html>
	<head>
	  <title>World Clock</title>
	  <script type="text/javascript" src="worldClockSolution.js"></script>
		
	  <style type="text/css">
		body {
		  font-family: sans-serif;
		  color: #333;
		}
		#container {
		  width: 400px;
		  margin: auto;
		}
		h1 { font-size: 5em; }
		select { font-size: 2em; }
	  </style>
	</head>

	<body>

	<div>
	  <h1 id="time">00:00:00</h1>      
	  
	  </div>

	</div> 

	<hr>

	<form>
	  <input type="radio" id="timezone0" name="timezone" value="0" checked>London</input>
	  <input type="radio" id="timezone1" name="timezone" value="1" >Paris</input>
	  <input type="radio" id="timezone2" name="timezone" value="2" >Athens</input>
	  
	</form>
	  
	</body>
	</html>
	
	```
	
	When another city in a different timezone is clicked the correct time for that timezone should appear.

	Ask the lecturer to demonstrate the functionality. 
	
	London=GMT, Paris=GMT+1, Athens=GMT+2
	

1.	In the (unlikely) event that you should run this program after 2200 hours make the necessary 
	modifications to ensure the hour time never shows 24 or 25 when the hours for Paris and Athens time are chosen. 

