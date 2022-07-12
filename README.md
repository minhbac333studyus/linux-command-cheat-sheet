# linux-command-cheat-sheet
## Check battery 
 
        sudo apt-get install acpitool
        acpi -V
 
    or
 
        upower -i /org/freedesktop/UPower/devices/battery_BAT0
 
## Close lid without shutdown
  Open the /etc/systemd/logind.conf file in a text editor as root, for example,

  sudo -H gedit /etc/systemd/logind.conf
If HandleLidSwitch is not set to ignore then change it:

  HandleLidSwitch=ignore
Make sure it's not commented out (it is commented out if it is preceded by the symbol #) or add it if it is missing.

Restart the systemd daemon (be aware that this will log you off) with this command:

  sudo systemctl restart systemd-logind
or, from 15.04 onwards:

  sudo service systemd-logind restart
