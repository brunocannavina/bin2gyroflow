# bin2gyroflow
Arduino code to read data from a gyroscope and accelerometer (MPU9250) and create the input file needed for Gyroflow.

This code is designed to be implemented on a Canon EOS M camera. Therefore, it also has the ability to start and stop recording simultaneously with data collection using an infrared LED.
In this way it will be easier to synchronize video with data.

## Arduino wiring

´´´
 MPU9250 <----> ARDUINO
   VIN   <---->   3.3V
   GND   <---->   3.3V   
   SDA   <---->   SDA
   SCL   <---->   SCL

  BUTTON <---->   D0 (and GND)
  IR LED <---->   D1
´´´

This sketch collects sensor data at 500hz and stores it on an SD card in a .bin file.
A Python script transforms it into a .csv file and another one .gcsv in the order and with the information needed for Gyroflow.

## How to transform bin file

To run the python script use the following code:

python bin2flow.py data01.bin

where data01.bin will depend on which file you are reading
Or drag the .bin file over the bin2flow.exe if you don't have Python installed on your computer.

And that's it, I'm leaving you a sample file so you can transform it and the corresponding video so you can try it in Gyroflow.

