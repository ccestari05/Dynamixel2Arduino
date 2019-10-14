# Dynamixel2Arduino [![Build Status](https://travis-ci.org/ROBOTIS-GIT/Dynamixel2Arduino.svg?branch=master)](https://travis-ci.org/ROBOTIS-GIT/Dynamixel2Arduino/branches)

## Serial and Direction Pin definitions by board
 - The examples default to pins based on DynamixelShield. Therefore, when using hardware other than DynamixelShield (eg OpenCM9.04, OpenCR, Custom DXL boards), you need to change the Serial and Direction Pin.
 - We provide the information below to make it easier to define Serial and Direction pins for specific hardware.

    |Board Name|Serial|Direction Pin|Note|
    |:-:|:-:|:-:|:-:|
    |OpenCM9.04|Serial1|28|because of the OpenCM 9.04 driver code, you must call Serial1.setDxlMode(true); before dxl.begin();.|
    |OpenCM9.04 EXP|Serial3|22||
    |OpenCR|Serial3|84||

## How to add new DYNAMIXEL model.
 - For the convenience of the user, Dynamixel2Arduino API hardcodes some information in the control table and stores it in flash.
 - To do this, you need to add code to some files. In this regard, please refer to [PR#3](https://github.com/ROBOTIS-GIT/Dynamixel2Arduino/pull/3) and [PR#7](https://github.com/ROBOTIS-GIT/Dynamixel2Arduino/pull/7)

## How to create custom PortHandler Class
 - Please refer to [port_handler.h](https://github.com/ROBOTIS-GIT/Dynamixel2Arduino/blob/master/src/utility/port_handler.h)
 - Create a new class by inheriting PortHandler as public. (Like SerialPortHandler and USBSerialPortHandler)

## TODO
 - Separation of protocol codes (protocol, packet handler)