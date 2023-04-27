# 24 Wrap-up

## 2023-04-27

### Agenda

- fetch redux
- jQuery magic
- onclick
- wrapup


### Useful resources

### Notes

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

    </body>
</html>
```
