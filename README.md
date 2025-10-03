The only change made is in the ./src/applayout/photoscreen1.py  ->  on_enter

This is thanks to Hamburguesa from Discord and https://kivyschool.com/. He provided me with this solution

This is made so it works for linux (wsl)

If working on wsl follow these instructions:
- On windows poweshell run:
- 	Get-CimInstance Win32_PnPEntity | ? { $_.service -eq "usbvideo" } | Select-Object -Property PNPDeviceID, Name
- 		This will get you your cameras ID and names
- 	ffmpeg -f dshow -rtbufsize 2147.48M -i video="YOUR_CAMERA_NAME" -framerate 30 -f mjpeg -q:v 5 tcp://0.0.0.0:8090?listen
- 		This will make the camera unavailable to windows and ready for WSL
  
