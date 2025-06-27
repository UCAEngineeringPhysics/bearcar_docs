# Autopilot Training Guide

> __On Server__

## Deep Learning Server Remote Log In

```bash
ssh USERNAME@192.168.0.112
```

## First Time Server Setup

```bash
cd ~
git clone https://github.com/UCAEngineeringPhysics/BearCar.git
cd ~/BearCar
./setup_pi_env.sh
```

## Start Training

```bash
cd ~/BearCar/scripts
uv run learn.py YYYY-MM-DD-HH-MM
```

Trained autopilot models will be saved on server at `~/BearCar/data/YYYY-MM-DD-HH-MM/models/`.
The best model candidate will be saved at `~/BearCar/data/YYYY-MM-DD-HH-MM/best_model.pth`.


## Transfer Model Back to RPi

```bash
rsync -av --partial ~/BearCar/data/YYYY-MM-DD-HH-MM/best_model.pth USERNAME@192.168.0.IP:~/BearCar/models/pilot.pth
```

## Choose Other Models
There are chances you are not satisfied with the `best_model` picked automatically by the `learn.py`.
To take a peek on all the models, you will want to list all of them using following commands:

```bash
cd ~/BearCar/data/YYYY-MM-DD-HH-MM/models
ls
```

An example is as below,

```console
ep10-mse0.3155.pth  ep2-mse0.3539.pth  ep5-mse0.3169.pth  ep8-mse0.3158.pth
ep11-mse0.3135.pth  ep3-mse0.3436.pth  ep6-mse0.3100.pth  ep9-mse0.3174.pth
ep1-mse0.3611.pth   ep4-mse0.3288.pth  ep7-mse0.3121.pth  learning_curve.png
```

The default best model is `ep6-mse0.3100.pth`.
This model may not work out.
So, you want to try your second best model __before__ the default, which should be `ep5-mse0.3169.pth`.
Then, transfer it to Raspberry Pi


```bash
rsync -av --partial ~/BearCar/data/YYYY-MM-DD-HH-MM/models/ep5-mse0.3169.pth USERNAME@192.168.0.IP:~/BearCar/models/pilot.pth
```

This will replace the previous best model on your Raspberry Pi though.
