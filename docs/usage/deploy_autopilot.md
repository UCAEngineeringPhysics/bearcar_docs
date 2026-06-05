# Autopilot Deploying Guide


__On Raspberry Pi__

## Autopilot On Duty
```bash
cd ~/BearCar/scripts
uv run drive.py --model pilot
```

!!!tip
    The `drive.py` will look for model file in `~/BearCar/models/` directory and the default autopilot file name is `pilot.pth`.
