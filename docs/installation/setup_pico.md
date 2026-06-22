# Setup Raspberry Pi Pico (2)

## Hardware List

- A Raspberry Pi Pico 2 development board (Pico).
- A Raspberry Pi (5).
- A Micro-USB cable.

## Install MicroPython Firmware

!!! note

    Raspberry Pi Foundation has a very detailed and easy-to-follow guide allowing people to [get started using Pico](https://projects.raspberrypi.org/en/projects/getting-started-with-the-pico).

Fire up Thonny IDE on your Raspberry Pi then execute following steps.

1. Click the bottom right corner of Thonny (where shows "Local Python 3"), then select "Install MicroPython"
2. In the pop-out window, make sure the "Target volume" is automatically recognized and the "Target model" is set to "Raspberry Pi RP2350" or similar.
3. Select "RP2" as the "MicroPython family", "Raspberry Pi Pico 2" as the "variant", "1.28.0" as the "version".
4. Click "Install" button to add MicroPython firmware to your Pico board.

## Set Up MicroPython Scripts

1. Install `rshell` to MicroPython scripts.

    ```console
    sudo apt install python3-pip
    pip install rshell --break-system-packages
    ```

2. Download [bearcar_pico](https://github.com/UCAEngineeringPhysics/bearcar_pico) repository

    ```console
    cd ~
    git clone https://github.com/ucaengineeringphysics/bearcar_pico.git
    cd bearcar_pico
    ```

3. Upload action and perception modules.

    ```console
    rshell -p /dev/ttyACM0 --buffer-size 512 cp -r upython_scripts/perception /pyboard/
    rshell -p /dev/ttyACM0 --buffer-size 512 cp -r upython_scripts/action /pyboard/
    ```

4. Upload the main script.

    ```console
    rshell -p /dev/ttyACM0 --buffer-size 512 cp upython_scripts/pico_interface.py /pyboard/main.py
    ```

## ESC Calibration

In order to get [Quicrun 1060 brushed ESC](https://www.hobbywing.com/en/products/quicrun-wp-1060-brushed55) cooperating with Pico, a calibration needs to be done before the first time using it.
Plug the ESC to a compatible battery pack, then execute the following steps.

1. Switch off ESC.
2. Unplug Pico from Raspberry Pi.
3. Plug Pico back into Raspberry Pi.
4. Turn ESC back on (you'll hear two shot beeps).
5. Open up Thonny IDE, click the STOP button twice.
6. Run [calibration script](https://github.com/UCAEngineeringPhysics/bearcar_pico/blob/main/upython_scripts/calibrate_esc.py) in Thonny.

## Troubleshooting: Nuke Pico ("Factory Reset")

In case of the Pico gets frozen or is doing anything unexpected.
You may want to [reset](https://www.raspberrypi.com/documentation/microcontrollers/pico-series.html#reset-flash-memory) the Pico board.

1. Download the [`nuke_universal.uf2`](https://github.com/raspberrypi/pico-sdk-prebuilts/releases/latest/download/nuke_universal.uf2) file.
2. Hold the white button on the Pico board while plug the Pico into the computer until the Pico is recognized as a external storage device.
3. Drag and drop (copy and paste) the `nuke_universal.uf2` file to the external storage device.

Now, you can repeat the steps in the previous section: [Install MicroPython Firmware](#install-micropython-firmware).
