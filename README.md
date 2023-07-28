# Music Manager Installation Guide

Music Manager allows you to add custom background songs that can play during Setup, Gameplay, and when a bomb explodes or is defused.

1. Subscribe to [Music Manager](https://steamcommunity.com/sharedfiles/filedetails/?id=1307302019&searchtext=music+manager) on the Steam Workshop
2. Launch the game at least once with the mod installed.
3. Close the game
3. Create a folder that will hold your music tracks
    - The name and location of the folder is not important
 4. Download this file and put it in your Tracks folder (**insert file**)
4. Insert your music tracks into your Tracks folder.

5. Adjust the volume of your tracks via an audio editor
    - The volume you hear in the editor will be the volume you hear in game when the music volume is set to 100%.
    
    - The compatible file types are **.wav** and **.ogg**

1. Open the **txt** file in an text editor

8. Copy the path of your track folder

6. Replace `INSERT YOUR FILE PATH HERE` with the path you just copied

1. Update your path
    - For each `\` in the path, replace it with a `/`
        - EX: `C:\Users\username\Desktop\Tracks` -> `C:/Users/username/Desktop/Tracks`
    
    - Add `"` around your path
        - EX: `C:/Users/username/Desktop/Tracks` -> `"C:/Users/username/Desktop/Tracks"`

1. For each music track you want added to the game, copy the file path to the track **including** the file type and paste it in its respective group. Replace `\` with `/`. Put `"` around your path the same way you did for the path to the folder.

    - EX: Setup room (the place when you are choosing a bomb): 
    ```	
    "Setup": {
        "Tracks": [
            "C:/Users/username/Desktop/Tracks/Setup.ogg"
        ],
        "AllowDefaults": false
    },
	```
    - EX: Gameplay room (the place when you are defusing a bomb): 
    ```	
    "Gameplay": {
        "Playlists": [
            {
                "Tracks": [
                    "C:/Users/username/Desktop/Tracks/Gameplay.ogg"
                ],
                "TracksFolder": "C:/Users/username/Desktop/Tracks",
                "Name": "MyGameplayPlaylist"
            }
        ],
        "AllowDefaults": false
    },
	```
    - EX: Successful Defusion
    ```
    "PostGameWin": {
        "Tracks": ["C:/Users/username/Desktop/Tracks/Win.ogg"],
        "AllowDefaults": false
    },
	```
    - Ex: Explosion
    ```	
    "PostGameLose": {
        "Tracks": ["Loss.ogg"],
        "AllowDefaults": false
    }
	```
	
 ### Multiple tracks in the same group
 
 If you want to have multiple tracks to play in a room as playlist, add a `,` between track names

- EX: This will play `Music1` and `Music2` in the Setup Room
    ```
    "Setup": {
        "Tracks": [
            "C:/Users/username/Desktop/Tracks/Music1.ogg",
            "C:/Users/username/Desktop/Tracks/Music2.ogg"
        ],
        "AllowDefaults": false
    },
    ```
    
13. Go to your `Modsetting` folder

    **For Windows**   
    
    - 1. Press `Win` + `R`
    - 2. Type in `%AppData%`
    - 3. Move out one folder to be in your `AppData` folder
    - 4. Move to `LocalLow` -> `Steel Crate Games` -> `Keep Talking and Nobody Explodes` -> `Modsettings`
1. Move the `txt` file in the `Modsetting` folder 
    - Say yes if it asks are you sure you want to overwrite the file
    
### Misc. Notes
- You will hear the default music in the Setup room until you exit out of a bomb
- If you change the location of your Tracks folder, you will need to update all the paths to where it currently is
- If you want the default music to play for a certain room, change the value after `AllowDefaults` from `false` to `true` 
