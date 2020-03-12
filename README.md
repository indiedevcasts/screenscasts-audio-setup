<p align="center">
    <a href="https://www.patreon.com/indiedevcasts" target="_blank">
        <img src="https://avatars2.githubusercontent.com/u/41526426?s=150"/>
    </a>
</p>

# About Indiedevcasts
> <a href="https://www.indiedevcasts.com" target="_blank">Indiedevcasts</a> is a All-in-One gamedev platform. It's kinda like your online library related to video games stuff! Subscribe now to get a free premium month!

# Screencast setup (audio + video)
## Setup
### ShareX
- Download [ShareX](https://getsharex.com/).
- Install ffmpeg from ShareX
- Install "screen-capture-recorder" and "virtual-audio-capture" from `Task Settings > Screen Recorder > Screen Recording options`
- Choose GDI Grab for the video
- Then get the name of your microphone by using the ffmpeg program previously installed :
```powershell
.\ffmpeg.exe -list_devices true -f dshow -i dummy
```
- Last step : update the ffmpeg command to configure your resolution, your microphone, your channels, and the mapping of the video and the audio channels. Here an example of my configuration with a RODE microphone :

```
-y -f dshow -i audio="Microphone (RODE NT-USB)" -f dshow -i audio="virtual-audio-capturer" -f gdigrab -framerate 30 -video_size 1920x1080 -draw_mouse 1 -i desktop -filter_complex "[0:a][1:a]amerge=inputs=2[a]" -map 2 -map "[a]" "$output$"
```
### Use a specific user session
- Use a specific user session for your screenscasts (no personal information, a personalized wallpaper, ...)
- Hide your desktop icons
- Hide your taskbar
- If you show code lines, or any kind of text, configure your zoom to 125% (works well with 1080p). Think about people looking your video on their smartphone
- Disable your notifications

# Podcasts setup
- Download [Audacity](https://audacity.fr/)
- Configure your Hz depending on your microphone. 48000Hz works well with the RODE NT-USB microphone
- Use a pop filter

# Video editing
- Download [Shotcut](https://shotcut.org/)
- I have not any specific recommandation here (feel free to update the readme)

> Shotcut is a free, open source, cross-platform video editor.
