# 24 Wrap-up

## 2023-04-27

### Agenda

- fetch redux
- jQuery magic
- onclick
- wrapup


### Useful resources

### Notes

Here is the partial interface HTML that we were looking at in class. 

```index.html
<html>
    <head>
        <title>Rock</title>
		<link href="./styles.css" rel="stylesheet">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.4/jquery.min.js"></script>
		<script src="./scripts.js"></script>
        <!-- Link to your script file(s) and CSS in here somewhere -->
    </head>
    <body onload="showHideShots()">

		<form id="userinput" class="" action="javascript:void(0);">
			<input type="radio" id="rps" name="game" value="rps" checked="checked" onclick="showHideShots()">
			<label for="rps">Play rock, paper, scissors?</label>
			<br/><br/>
			<input type="radio" id="rpsls" name="game" value="rpsls" onclick="showHideShots()">
			<label for="rpsls">Play rock, paper, scissors, lizard, Spock?</label>
			<br/><br/>
			<input type="checkbox" id="opponent" name="playtype" value="opponent" onclick="showHideShots()">
			<label for="opponent">Play against an opponent?</label>
			<br/><br/>
			<input type="radio" id="rock" name="shot" value=rock" class="rps shots" checked="checked">
			<label class="shots rps">Rock</label>
			<input type="radio" id="paper" name="shot" value="paper" class="rps shots">
			<label class="shots rps">Paper</label>
			<input type="radio" id="scissors" name="shot" value="scissors" class="rps shots">
			<label class="shots rps">Scissors</label>
			<input type="radio" id="lizard" name="shot" value="lizard" class="rpsls shots">
			<label class="shots rpsls">Lizard</label>
			<input type="radio" id="spock" name="shot" value="spock" class="rpsls shots">
			<label class="shots rpsls">Spock</label>
<!--			<br/><br/>
			<input type="submit" id="play" name="controls" value="Play">
      <input type="submit" id="startover" name="controls" value="Start Over"> -->
		</form>
		<br/><br/>
    <button type="button" id="play" onclick="playGame()">Play</button>
    <button type="button" id="startover" onclick="startOver()">Start Over</button>

    <!-- Your interface markup goes here -->
    <!-- For interface examples, look in the `/examples/` directory in the root of your starter code repo. -->
    
    <!-- You will want to include something hidden by default, like a <div> or <p> that you can show to -->
    <!-- display the results of the game. Your startOver() function should also clear the result and hide -->
    <!-- the block again. -->

    </body>
</html>
```

This is the nominally functional JavaScript that will at least return data from a properly configured API. 

```scripts.js
// This function shows and hides the shot selection in the interface based 
// on whether or not the #opponent checkbox is checked
function showHideShots() {
// Get the info from the checkbox
  	let check = document.getElementById('opponent');
// Check if the checkbox is checked and show or hide options accordingly
	if (check.checked == true) {
// Here, instead of just showing all of the options, use similar logic to 
// check which of the game radio buttons is checked and show only those
// options relevant to the game being selected (rps or rpsls). You can 
// use similar jQuery 
		$('.shots').show()
	} else {
		$('.shots').hide()
	}
}
// This function clears the input form and also resets the shot selection
// radio buttons. 
function startOver () {
	document.getElementById('userinput').reset();
	showHideShots();
}

async function playGame () {
	// Get which game is being played based on the value in the form
	let game = $('input[type=radio][name=game]:checked').val();
	// Get which shot is being played based on the value in the form
	let shot = $('input[type=radio][name=shot]:checked').val();
	// Identify the base URL based on browser information
	let baseurl = window.location.href + 'app/'
	// Log the base URL
	console.log(baseurl)
	// This constructs a URL for the opponent option ONLY. To incorporate
	// the other option, you can use a conditional to change the URL based
	// on what is selected. You could also write separate functions, or use
	// a conditional somewhere above in this function to construct the 
	// correct URL
	let url = baseurl + game + '/play/' + shot
    // Log the full URL
	console.log(url)	

	let response = await fetch(url)
	let result = await response.json()
	// Log the result
	console.log(result)
	// Here you should include code that uses the DOM API or jQuery to 
	// manipulate another block of HTML in the interface to display the 
	// results in some way. 
}
```
