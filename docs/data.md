# Data Collection Guide

> __All in Raspberry Pi__

## Start Tele-Operation

```bash
cd ~/BearCar/scripts
uv run teleop.py
```

## Hints

- Press `Pause` button to start/pause BearCar.
- Press `Record` button to activate/deactivate data recording.
- Data will be saved to `~/BearCar/data/YYYY-MM-DD-HH-MM/`
- Valid data directory contains: `~/BearCar/data/YYYY-MM-DD-HH-MM/images/` directory and `~/BearCar/data/YYYY-MM-DD-HH-MM/labels.csv` file.

> `YYYY-MM-DD-HH-MM` is the date and time when you start the `teleop.py`.
> For example, `2000-01-02-03-04`

## Data Transfer

To train a autopilot faster, you will need to transfer your data to a deep learning server.
For example:

```bash
rsync -av --progress --partial ~/BearCar/data/YYYY-MM-DD-HH-MM USERNAME@192.168.0.112:~/BearCar/data/
```

> - Please replace `YYYY-MM-DD-HH-MM` with actual date and time of the data directory
> - Please replace `USERNAME` with your username on the deep learning server.
> - Syntax:
```bash
rsync -av --progress --partial <path_to_stamped_data> <username>@<ip_address>:<bearcar_directory>/data/
```

