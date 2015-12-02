#SoundManager

**This is old.** You'd better use [`howler.js`](http://goldfirestudios.com/blog/104/howler.js-Modern-Web-Audio-Javascript-Library)

Javascript Sound Manager - Works on most of the browser and supports multi channel.

##How to :

1. Initialize the sound manager with your base sound path

		soundManager.init("snds/"); // Your base sound path


2. Create an object containing your sound references and url. The sound manager finds the extension : 
	
		var mySounds = [
			["mainMusic", "music1"], // mainMusic is the reference you will use to play the song, and music1 its path
			["loseSound", "sfx/gameover."]
		];
		soundManager.pushSounds(mySounds); 

3. Check if the sounds are loaded :
	
		soundManager.isLoaded(); // True if loading is finished, else false

4. If your sounds are loaded, use them !
	
		soundManager.play('mainMusic');


5. You can do a lot of  other things, like :
	
	1. Activation / Desactivation

		    soundManager.desactivate('mySound'); // Desactivates (and mute) the sound
		    soundManager.activate('mySound'); // Reactivates (and unmute) the sound
		    soundManager.pause('mySound'); // Pauses the sound. Use play to relaunch the sound.
		    soundManager.shutDown(); // Shuts down the sound manager (stops any sound) or, if already shutdown, reactivates it.

	2. Volume

		    soundManager.setVolume('mySound'); // Sets the volume of a sound - Between 0 and 1
		    soundManager.lowVolume(); // Lower the volume by 10%
		    soundManager.upVolume(); // Up the volume by 10%

	3. Loading

		    soundManager.getLoadPercentage(); // Returns the current loading percentage, if for exemple you wanna make a loading bar.
