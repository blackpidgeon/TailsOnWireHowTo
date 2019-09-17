# Installing Wire on Tails
Wire is an encrypted messaging app, available for many different platforms.
It is possible to install on Tails, a secure Linux on an USB Stick.

## Configure Tails
You will need a Persistent Volume. Check the Tails docs if you need to create one

#### Enable Persistent Dotfiles. 
1. Open the "Configure Persistent Volume" application. You find it in the Tails application menu in the Group named "Tails".
2. Enable "Dotfiles" at the bottom of the list and Save the changes.

## Download Wire
1. Go to https://wire.com/en/download/
2. Click on Details
3. Choose AppImage

## Install the AppImage
1. Create a folder called "Wire" in your Persistent folder.
1. Move the downloaded file into your this folder, and rename it to ``Wire.AppImage``
2. Create two empty folders next to it, and name them ``Wire.AppImage.config`` and ``Wire.AppImage.home``. This ensures that your conversations are saved in your Persistent folder, and you don't have to login each time again.
3. Create a file called ``Wire.desktop`` with the following content:
````
[Desktop Entry]
Encoding=UTF-8
Name=Wire
Exec='/home/amnesia/Persistent/Wire/Wire.AppImage' --proxy-server="socks5://localhost:9050"
Type=Application
Categories=Network;
````
4. Install the Wire.desktop link by running the following two commands in the command line:
````
mkdir -p "/live/persistence/TailsData_unlocked/dotfiles/.local/share/applications"
cp "/home/amnesia/Persistent/Wire/Wire.desktop" "/live/persistence/TailsData_unlocked/dotfiles/.local/share/applications"
````
## Done
After a reboot you should find Wire as an entry in the Tails Application menu (category Network)
