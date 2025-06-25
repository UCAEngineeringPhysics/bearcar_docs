# Autopilot Training Guide

## Deep Learning Server Remote Log In

```bash
ssh USERNAME@192.168.0.112
```

## First Time Server Setup

```bash
cd ~
rm -rf ~/BearCar
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

