# bitcoin-rpi

RPI Bitcoin install 

sudo apt-get -y install git-core build-essential autoconf automake libtool pkg-config nodejs libcurl4-gnutls-dev libjansson-dev uthash-dev libncursesw5-dev libudev-dev libusb-1.0-0-dev libevent-dev libmicrohttpd-dev libncurses5-dev unzip libblkmaker-0.1-dev

sudo git clone https://github.com/ckolivas/cgminer

cd cgminer

sudo ./autogen.sh -rpath-link

sudo chmod +x ./configure

sudo ./configure --enable-icarus --enable-bmsc

sudo make

sudo make install

sudo cp 01-cgminer.rules /etc/udev/rules.d/

sudo reboot

sudo ./cgminer -o stratum+tcp://stratum.slushpool.com:3333 -u wk.worker1 -p anypassword
