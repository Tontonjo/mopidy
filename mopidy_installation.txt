# Tonton Jo - 2020
# Join me on Youtube: https://www.youtube.com/channel/UCnED3K6K5FDUp-x_8rwpsZw

# Mopidy installation guide:
# Tested on the 30.11.2020 - there may have been some changes since:-)

sudo apt-get update
sudo apt-get upgrade

sudo wget -q -O - https://apt.mopidy.com/mopidy.gpg | sudo apt-key add -
sudo wget -q -O /etc/apt/sources.list.d/mopidy.list https://apt.mopidy.com/buster.list
sudo apt update
sudo apt install -y mopidy build-essential python3-dev python3-pip
sudo dpkg-reconfigure mopidy

sudo python3 -m pip install Mopidy-MusicBox-Webclient
sudo python3 -m pip install Mopidy-Subidy
sudo python3 -m pip install Mopidy-MPD

###########################################################

sudo mopidyctl config
sudo nano "/etc/mopidy/mopidy.conf"

sudo mopidyctl -vvvv

sudo service mopidy restart


###########################################################
# Pour utilisation avec une carte son:
sudo nano /boot/config.txt

disable_splash=1
hdmi_drive=2
dtparam=i2c_arm=on
dtparam=i2s=on
dtparam=audio=off
dtoverlay=iqaudio-dacplus,unmute_amp
#dtoverlay=pi3-disable-wifi
#dtoverlay=pi3-disable-bt
