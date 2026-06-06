# Autopilot Training Guide

> __On Raspberry Pi__

## Log in to the Server (Remotely and Securely)

```sh
ssh <username>@<ip_address>
```

### Example

```sh
ssh user@192.168.0.112
```

You can log in to the server by inputting correct password of it.

!!!tip
    You can localize yourself by looking at the command prompt displayed in the terminal: `<username>@<hostname>:<current_path>$`.
    The `<hostname>` part tells you which machine your are logged in (RPi or server).

## Start Training

> __On server__

```sh
cd ~/BearCar/scripts
uv run learn.py YYYY-MM-DD-HH-MM
```

Trained autopilot models will be saved on server at `~/BearCar/data/YYYY-MM-DD-HH-MM/models/`.
The best model candidate will be saved at `~/BearCar/data/YYYY-MM-DD-HH-MM/best_model.pth`.

## Transfer Model Back to RPi

> __On server__

```sh
rsync -av --partial <model_file_path> <username>@<ip_address>:<bearcar_path>/models/<desired_model_name>.pth
```

### Example

```sh
rsync -av --partial ~/BearCar/data/YYYY-MM-DD-HH-MM/best_model.pth USERNAME@192.168.0.IP:~/BearCar/models/pilot.pth
```

!!!tip
    You may need to find out the IP address of your Raspberry Pi using command: `ip r`

### Model candidates

There are chances you are not satisfied with the `best_model` picked automatically by the `learn.py`.
To take a peek on all the models, you can list all of them using following commands:

```sh
ls ~/BearCar/data/YYYY-MM-DD-HH-MM/models
```

For example,

```console
ep10-mse0.3155.pth  ep2-mse0.3539.pth  ep5-mse0.3169.pth  ep8-mse0.3158.pth
ep11-mse0.3135.pth  ep3-mse0.3436.pth  ep6-mse0.3100.pth  ep9-mse0.3174.pth
ep1-mse0.3611.pth   ep4-mse0.3288.pth  ep7-mse0.3121.pth  learning_curve.png
```

The model files are named as the format: `<epoch_number>-<loss_type><loss_value>.pth`.
The tailing value behind `mse` indicates the performance of the model during the training phase.
Theoretically, The lower the value is the better the model performed.
In this example, `ep6-mse0.3100.pth` was picked as the best model.
You can transfer the second best or any model among these candidates, e.g., `ep5-mse0.3169.pth` to Raspberry Pi.

```sh
rsync -av --partial ~/BearCar/data/YYYY-MM-DD-HH-MM/models/ep5-mse0.3169.pth USERNAME@192.168.0.IP:~/BearCar/models/newpilot.pth
```

### Learning curve

The learning curve is saved as `<bearcar_data_directory>/models/learning_curve.png`.
You would like to see a dropping curve instead of a climbing one.
Or, something was terribly wrong.

!!!tip
    You can log out of the server by using command: `exit` in the terminal or simply just hit `Ctrl`+`d`.
    Remember to check the computer you are using now.
