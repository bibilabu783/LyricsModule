# LyricsModule
LyricsModule - Apple Music–style animated song lyrics display 🎵 (for Roblox Studio) <br>
***Created by Claude***

### **USAGE** (from a LocalScript / Script):

`local LyricsModule = require(path.to.LyricsModule)` <br>
`LyricsModule.Play(frame, sound, lrcText)`  — minimal <br>
`LyricsModule.Play(frame, sound, lrcText, options)` — with options <br>
`LyricsModule.Stop()` — stop <br>
`LyricsModule.Clear()` — clear the frame <br>
`LyricsModule.ViewError(frame, message)` — show an error manually <br>

### Play() **PARAMETERS**:
frame : Frame — container the lines get parented to <br>
sound : Sound — audio source (uses .TimePosition) <br>
lrcText : string — text in LRC format (see example below) <br> 
options : table? — optional settings (see Options) <br>

### **LRC FORMAT:**

    [00:38.06] And the science gets done and you make a neat gun.
    [00:42.08] For the people who are still alive.
    [00:46.19]
    [00:52.06] I'm not even angry.
    [00:56.09] I'm being so sincere right now.

(empty line = pause marker)

### COUNTDOWN ("3, 2, 1" before a line):
- Before the very first line — shown automatically if the intro pause is longer than .countdownThreshold seconds. No empty line needed here.

- Mid-song — only if the LRC itself has an empty timestamped line between two real lines AND the gap after it is longer than .countdownThreshold. That empty line becomes a real, reserved blank line in the layout (not an overlay), so it can never cover up other lines — a long gap with no empty marker is left alone and stays silent.

### **OPTIONS** (all optional):
`.activeColor` : Color3 — active line color *(default: rgb(10,10,10))* <br>
`.inactiveColor` : Color3 — inactive line color *(default: rgb(150,150,150))* <br>
`.activeFontSize` : number — active line TextSize *(default: 42)* <br>
`.inactiveFontSize` : number — other lines' TextSize *(default: 23)* <br>
`.lineSpacing` : number — spacing between lines, px *(default: 20)* <br>
`.tweenTime` : number — animation duration, sec *(default: 0.4)* <br>
`.clearFrame` : bool — clear the frame before starting *(default: true)* <br>
`.font` : string — font name for Font.fromName *(default: "GothamSSm")* <br>
`.countdownThreshold` : number — min. pause length (intro or marked mid-song gap) for a countdown to show *(default: 3)* <br>

`.showErrorOnScreen` : bool — show errors inside the frame *(default: false)*<br> 
`.errorMessage` : string — validation error text *(default: built-in)* <br>
`.errorColor` : Color3 — error text color *(default: rgb(180,60,60))* <br>
`.errorFontSize` : number — error TextSize *(default: 20)* <br>
`.errorFont` : string — error font *(default: options.font or "GothamSSm")* <br>
`.errorFontWeight` : string — error font weight *(default: "SemiBold")* <br>
`.errorFadeTime` : number — error fade-in duration *(default: 0.3)* <br>

### DOWNLOAD:
See [Releases](https://github.com/bibilabu783/LyricsModule/releases) or via the [Creator Store](https://create.roblox.com/store/asset/139311602552784/LyricsModule)
