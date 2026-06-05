# Autopilot Deploying Guide


__On Raspberry Pi__

## Autopilot On Duty
```bash
cd ~/BearCar/scripts
uv run drive.py --model pilot
```

!!!tip
    - The `drive.py` will look for model file in `~/BearCar/models/` directory.
    - Use argument: `--model` to specify autopilot model file name.
    - Press `Pause` button to start/pause the autopilot.
