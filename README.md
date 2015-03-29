# RaspberryCast
> Transform your Raspberry Pi into a streaming device.
Videos can be sent from mobile devices or computers (Chrome extension).

Demo video 1 :

[![Alt text for your video](http://img.youtube.com/vi/0wEcYPSm_f8/0.jpg)](http://www.youtube.com/watch?v=0wEcYPSm_f8)

Demo video 2 :

[![Alt text for your video](http://img.youtube.com/vi/ZafqI4ZtJkI/0.jpg)](http://www.youtube.com/watch?v=ZafqI4ZtJkI)

## Supported services

Works with all youtube-dl supported websites: 
http://rg3.github.io/youtube-dl/supportedsites.html (YouTube, SoundCloud, Dailymotion, Vimeo, etc...) but also any mp3, mp4, avi and mkv file.

RasberryCast also works with PopcornTime.

## How to install (RaspberryPi side)

```
wget https://raw.githubusercontent.com/vincent-lwt/RaspberryCast/master/setup.sh && sudo sh setup.sh
```
That's it.

The installation script will:
- Install the necessary dependencies
- Install RaspberryCast
- Autostart RaspberryCast at boot (added to /etc/rc.local)
- Reboot (necessary to print logs on first use)

If you want to disable login at boot:
```
sed -i '/1:23/c\1:2345:respawn:/bin/login -f pi tty1 </dev/tty1 >/dev/tty1 2>&1' /etc/inittab
```

## Chrome extension (computers)

![alt tag](https://raw.githubusercontent.com/vincent-lwt/RaspberryCast/master/images/extension.png)

![alt tag](https://raw.githubusercontent.com/vincent-lwt/RaspberryCast/master/images/rightclick.png)

1. Download and extract https://github.com/vincent-lwt/RaspberryCast/archive/master.zip on your computer
2. Visit chrome://extensions in your browser 
3. Ensure that the Developer mode checkbox in the top right-hand corner is checked.
4. Click Load unpacked extension… to pop up a file-selection dialog.
5. Navigate to the directory /RaspberryCast/chrome (the folder you unpacked), and select it.
6. The option page will open, configure the Raspberry Pi ip.

Alternatively, you can drag and drop the directory where your extension files live onto chrome://extensions in your browser to load it.

You can configure settings in the option page.

# Remote control (mobile devices)

![alt tag](https://raw.githubusercontent.com/vincent-lwt/RaspberryCast/master/images/android.png)

On any device connected to the same network as you Pi, you can visit the page:
```
http://<your-Pi-ip>:2020/remote
```
"Add to homescreen" this page is recommended

## Use with PopcornTime

Use the following version: https://popcorntime.io/

First, you need to enable the PopcornTime support in the extension options

1. When the selected movie/show is playing click "u" (keyboard).
2. Open your browser, click on the extension and paste the URL in the textbox (ctrl-v).
3. Press enter, and wait a few seconds.

Keep Popcorntime running during play.


**Update:**

```
cd /RaspberryCast
sudo git pull
sudo ./RasberryCast.sh restart
```

**Todo:**

- Better errors handling
- Firefox extension
- Android/iOS app for control & sharing
- HDMI-CEC support

You are welcome to contribute to the project.
