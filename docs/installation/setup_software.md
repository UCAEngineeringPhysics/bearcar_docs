# Setup BearCar Software
???+ tip
    BearCar software setup commands work on both Raspberry Pi and Debian derived Linux.
    Unfortunately, Windows and Mac are note supported.

## Hardware List

- An assembled BearCar
- A Raspberry Pi (5).

!!! note
    Use the commands in a terminal emulator.
    You can bring up one by pressing `Ctrl` `Alt` `t`.

### Download BearCar from Github

```console
cd ~
git clone https://github.com/UCAEngineeringPhysics/BearCar.git
```

### Setup the Python environment

```console
cd ~/BearCar
./setup_env.sh
```

!!! tip
    If something went wrong, you can simply delete the BearCar directory
    ```console
    rm -rf ~/BearCar/
    ```
