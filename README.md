git clone https://github.com/aircrack-ng/rtl8188eus

cd rtl8188eus

sudo -i

echo "blacklist r8188eu" to  "/etc/modprobe.d/realtek.conf"

exit

sudo make

sudo make install

sudo modprobe 8188eu

iwconfig

---

sudo ifconfig wlan0 down
sudo airmon-ng check kill
sudo iwconfig wlan0 mode monitor

sudo ifconfig wlan0 up
iwconfig
