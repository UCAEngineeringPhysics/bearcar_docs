# Data Collection Guide

## Start Tele-Operation

```bash
cd ~/BearCar/scripts
uv run teleop.py
```

## Hints

- Press `Pause` button to start/pause BearCar.
- Press `Record` button to activate/deactivate data recording.
- Data will be saved to `~/BearCar/data/YYYY-MM-DD-HH-MM/`
- Valid data directory contains: `~/BearCar/data/YYYY-MM-DD-HH-MM/images/` directory and `labels.csv` file.

## Data Transfer

To train a autopilot faster, you will need to transfer your data to a deep learning server.
For example:

```bash
rsync -av --prgress --partial ~/BearCar/data/YYYY-MM-DD-HH-MM USERNAME@192.168.0.112:~/BearCar/data/
```
