-= Current Instructions for M8 Production and Beta unit owners =-

Windows (7/8/10/11) and MacOS:
Download & Install TyTools:
https://github.com/Koromix/tytools/releases

1. Unzip the Firmware. (Yay you did this!)
2. Plug in M8 via USB DO NOT USE A USB HUB IF IT CAN BE AVOIDED
3. Turn M8 on.
4. Close all other applications
5. Open "TyUploader" (previously called "TyUpdater" in old versions) - Note: "TyCommander" was also installed, don't use that.
6. Make sure "M8 [xxxxxxxx]" is selected in the dropdown if you have other Teensy devices plugged into your computer.
7. Click "Upload" select the .hex file from this zip file.


Note for Windows 7 - Download and install Teensyduino to install the USB driver needed for flashing M8 firmware:
https://www.pjrc.com/teensy/td_download.html


Linux

This assumes you are comfortable with terminal (no GUI)
Tested for Ubuntu 22.04.2 LTS

First, install `tycmd`

1. Clone the tytools git repository
2. Install dependencies for tytools
3. Build the `tycmd` binary
4. Test if build was successful

```
git clone https://github.com/Koromix/tytools.git
sudo apt-get install build-essential cmake libudev-dev qtbase5-dev pkg-config
cd tytools
mkdir -p build/linux && cd build/linux
cmake -DCMAKE_INSTALL_PREFIX=/usr/local ../..
make
./tycmd --version
# should show output like "tycmd 0.9.8-3-gcd37c1b"
```

Then:

1. Unzip the Firmware. (Yay you did this!)
2. Plug in M8 via USB DO NOT USE A USB HUB IF IT CAN BE AVOIDED
3. Turn M8 on.
4. Open your terminal & navigate to the build/linux directory (see tycmd installation steps)
5. Run `./tycmd list`
6. Make sure the only connected Teensy board is the M8.
You should see an output like "add 01234567-Teensy Teensy 4.0 (M8)"
7. Upload the firmware via `sudo ./tycmd upload PATH_TO_HEX_FILE`
