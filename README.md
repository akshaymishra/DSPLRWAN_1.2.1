# DSPLRWAN_1.2.1
DSPWorks LRWAN based on the ST I-Cube LRWAN 1.2.1

# ChariotLRWAN
ST LRWAN Stack which works with DSPWorks SX1262 Chariot board

# How to Use this Code
This code has been written for the DSPWorks Chariot2 (SX1262 and STM32L071CBT6) board. This revision is based on the ST I-Cube LRWAN.
The LRWAN Stack is 1.0.3

It has been written keeping System Workbench in mind. This code is for IN865, Indian Region. 
The board works on 3.3V (**3.6VDC is absolute maximum**). We designed it for battery based operations and hence this care may be essential for getting best out of your board


##### Recommended Batteries
1. LiSoCL2 is a battery we recommend which has been reliably tested. Please ensure it can provide atleast *100mA* of peak current

##### Performance
1. the Standby current is about 2.5 uA
2. The peak power is about 21.76 dBm
3. Range -- depends upon topology, antenna, battery power, ... ~1km is a good number to expect

### Requirements
Please install System Workbench, latest stable version. Get it here [System Workbench](https://www.openstm32.org/System%2BWorkbench%2Bfor%2BSTM32) which will install the compiler as well.

### Checkout/ Download this code 
This is usually in a folder where you'd like to set your workspace

### Steps
1. File --> Import...
2. Select General and then select Existing Projects into Workspace
3. In Select root directory: tab Browse to the parent folder 
4. You'll now see the project name **sx1262dvk1das** in the Projects window below
5. Select and Finish. 

This gets your workspace going

##### Modifications
You will have to set the following before the LRWAN node gets talking to any  of your gateway
file: Commissioning.h
1. set LORAWAN_APP_KEY as per your vendor/ gateway.
2. IEEE_OUI is the **3** byte prefix. Set this to *anything* if its your local gateway. 
3. LORAWAN_DEVICE_EUI as per your vendor/ gateway.

#### Build and Flash it to your board.


## How to setup your CharIoT2 hardware
1. The CharIoT2 [Datasheet](https://github.com/akshaymishra/ChariotLRWAN/blob/master/Documents/Datasheet-CharIoT2.1.pdf) has all the details on the device
2. Attach a 5-pin header if your board did not come pre-populated with this header
3. Attach the power header **J9**. 
4. **THERE IS NO REVERSE POLARITY PROTECTION ON THIS BOARD**
5. Apply power (3.3V -- maximum is 3.6V). 
6. Connect ST-link v2. 


#### Troubleshooting
If you are unable to connect to the board, please check the following

1. Download the STM32 ST-Link Utility
2. Connect the STLink/v2 to the board and your PC
3. Ensure Connect under Reset is enabled in your Settings for ST-Link Utility
4. Connect to the board. If this results in a success, it usually would mean there is some settings related issue in  System Workbench
