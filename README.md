# 1. ZED-jetson
This repositary will guide you to use the Nvidia Jetson nano development kit with the ZED camera to create a 3D map of the surrounding and to be used for navigation.
# 1.1 Jetson nano Installation
The Jetson Nano Developer Kit uses a microSD card as a boot device and for main storage. It’s important to have a card that’s fast and large enough for your projects; the minimum recommended is a 16GB.
## Write Image to the microSD Card
To prepare your microSD card, you’ll need a computer with Internet connection and the ability to read and write SD cards, either via a built-in SD card slot or adapter.

1. Download the [Jetson Nano Developer Kit SD Card Image](https://nvidia.box.com/shared/static/dp7xma0f4jbvttha6xo14km14fztal7o.zip), and note where it was saved on the computer.
2. Write the image to your microSD card by following the instructions below according to the type of computer you are using: Windows, Mac, or Linux. 
### Windows

1.    Download, install, and launch [SD Memory Card Formatter](https://www.sdcard.org/downloads/formatter/) for Windows.
2.    Select card drive
3.    Select “Quick format”
4.    Leave “Volume label” blank
5.    Click “Format” to start formatting, and “Yes” on the warning dialog

#### Use Etcher to write the Jetson Nano Developer Kit SD Card Image to your microSD card

   1. Download, install, and launch [Etcher](https://www.balena.io/etcher/).
   2. Click “Select image” and choose the zipped image file downloaded earlier.
   3. Insert your microSD card if not already inserted.
   5. Click “Select drive” and choose the correct device.
   6. Click “Flash!” It will take Etcher about 10-20 minutes to write and validate the image if your microSD card is connected via USB3.
   7. After Etcher finishes, Windows may let you know it doesn’t know how to read the SD Card. Just click Cancel and remove the microSD card.

