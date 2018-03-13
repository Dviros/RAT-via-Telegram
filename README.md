# RAT-via-Telegram
## Dviros's notes:
Windows Remote Post Breach Tool via Telegram (Python 2.7),
Originally created by <a href="http://github.com/Ritiek">Ritiek</a>, Forked and modified by <a href="http://github.com/mvrozanti">mvrozanti</a> and then myself.

The whole purpose of this tool is to demonstrate (as a "PoC") the control of an already breached machine, via Telegram.
As the same with my already written tools, I do not promote illegal activities.

This modified version uses Telegram bot API v2, instead of the traditional v1. The main change is keyboard buttons instead of text typing.
I will try to add new features, close bugs and be compatible to the API v3, after adding the needed changes from "mvrozanti".
In the meanwhile, cd, download, upload, run and delete commands will not work.


## Donations will be highly appreciated
![Monero Donation](https://i.imgur.com/AMK3OCh.png)

### Currently Working Features:

- Run keylogger on the target
- Get target PC's Windows version, processor and more
- Get target PC's IP address information and approximate location on map
- [WIP] Delete files or folder on target
- Show current directory on target
- [WIP] Change current directory on target
- List current or specified directory on target
- [WIP] Download any file from the target
- Upload local files to the target. Send your image, pdf, exe or anything as `file` to the Telegram bot
- Autostart playing a video in fullscreen and no controls for a youtube video on target
- Screenshots of the target
- [WIP] Execute any file on the target
- Access to microphone on target
- Start HTTP Proxy Server
- Freeze target's keyboard
- Return the target's ARP table
- [WIP] Schedule tasks to run at specified time
- [WIP] Freeze target's mouse
- Get active processes and services
- [WIP] Capture clipboard (Text, Image)
- [WIP] Disable/Enable mouse/keyboard
- [WIP] Hide desktop icons
- [WIP] Update .exe on target
- [WIP] Shutdown \ Reboot computer
- [WIP] Self-Destruct RAT on the target
- [WIP] Take snapshots from the webcam (if attached)
- [WIP] Copy and Move files on the target
- [WIP] Audio compression
- More coming soon!



## Ritiek's legacy notes:
### Why another one?

- The current Remote Administration Tools in the market face 2 major problems:

    - Lack of encryption.
    - Require port forwarding in order to control from hundreds of miles.

- This RAT overcomes both these issues by using the Telegram bot API.

    - Fully encrypted. The data being exchanged cannot be spied upon using MITM tools.
    - Telegram messenger app provides a simple way to communicate to the target without configuring port forward before hand on the target.


## Screenshots:

<img src="http://i.imgur.com/I5nzrbz.jpg">

## Installation & Usage:

- Clone this repository.
- Set up a new Telegram bot talking to the `BotFather`.
- Copy this token and replace it in the beginning of the script.
- Install the dependencies: `pip install -r requirements.txt`.
- Install pyHook `64-bit` or `32-bit` depending on your system.
    - For 64-bit- `pip install pyHook-1.5.1-cp27-cp27m-win_amd64.whl`.
    - For 32-bit- `pip install pyHook-1.5.1-cp27-cp27m-win32.whl`.
- To run the script: `python RATAttack.py`.
- Find your bot on telegram and send some command to the bot to test it.
- To restrict the bot so that it responds only to you, note down your `chat_id` from the console and replace it in the script and comment out the line `return True`. Don't worry, you'll know when you read the comments in the script.
<img src="http://i.imgur.com/XKARtrp.png">
- A folder named `RATAttack` will be created in your working directory containing `keylogs.txt` and any files you upload to the bot.


## Compiling:

### How To Compile:
#### Either:
	Replace your path in compileAndRun.bat (running this will actually run the executable)
#### Or:
	Run `pyinstaller --onefile --noconsole C:\path\to\RATAttack.py`. You can also pass `--icon=<path\to\icon.ico>` to use any custom icon.
- Once it is compiled successfully, find the `.exe` file in `C:\Python27\Scripts\dist\`. You can change the name of the `.exe` to anything you wish.
- **BEWARE!** If you run the compiled `.exe`, the script will hide itself and infect your PC to run at startup. You can return to normal by using the `/self_destruct` option or manually removing `C:\Users\Username\AppData\Roaming\Portal` directory and `C:\Users\Username\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\portal.lnk` (although I recommend removing them manually for the time being).

### Modifying Settings:

- You can also modify the name of hidden `.exe` file and location & name of the folder where the hidden `.exe` will hide itself. To do this; modify `compiled_name` and `hide_folder` respectively.
- Assign your known chat ids to beginning of RATAttack.py



## License:

`The MIT License`
