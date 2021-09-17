sudo add-apt-repository ppa:blaze/rtbth-dkms

sudo apt update

sudo apt install rtbth-dkms

sudo vim /etc/rc.local


## ADD THE COMMAND RIGHT BEFORE "EXIT 0" AND SAVE.

modprobe rtbth &> /dev/null 


## DE VOLTA AO TERMINAL


sudo chmod 777 /etc/rc.local

sudo apt install blueman


## REBOOT


sudo /etc/init.d/bluetooth start

systemctl start bluetooth

sudo modprobe btusb 

sudo systemctl start bluetooth.service

sudo service bluetooth restart
