# Pilot Configuration

We use `scripts/configs.json` to configure the BearCar's driving experience for both human and non-human pilots.

## `steering_joy_axis`

__Default Value:__ 0

__Pilot Modes:__ `teleop`

Index number of the joystick axis on gamepad for steering BearCar.

## `throttle_joy_axis`

__Default Value:__ 4

__Pilot Modes:__ `teleop`

Index number of the joystick axis on gamepad for propelling BearCar.

## `record_btn`

__Default Value:__ 5

__Pilot Modes:__ `teleop`

Index number of the gamepad button for activate/deactivate data recording.

## `pause_btn`

__Default Value:__ 4

__Pilot Modes:__ `teleop`, `autopilot`

Index number of the gamepad button for pause/resume driving.

## `stop_btn`

__Default Value:__ 0

__Pilot Modes:__ `teleop`, `autopilot`

Index number of the gamepad button for emergency stop (__terminates program__).

## `steering_left`

> Deprecated

## `steering_right`

> Deprecated

## `steering_center`

__Default Value:__ 15000000

__Pilot Modes:__ `teleop`, `autopilot`

Pulse width for centering the steering servo (unit: nanosecond).

## `steering_range`

__Default Value:__ 300000

__Pilot Modes:__ `teleop`, `autopilot`

Max pulse width increment/decrement from steering center.

## `throttle_neutral`

__Default Value:__ 15000000

__Pilot Modes:__ `teleop`, `autopilot`

Pulse width for 0 throttle (unit: nanosecond).

## `throttle_fwd_range`

__Default Value:__ 3000000

__Pilot Modes:__ `teleop`, `autopilot`

Max pulse width increment throttle from neutral to drive BearCar forward.

## `throttle_rev_range`

__Default Value:__ 4000000

__Pilot Modes:__ `teleop`, `autopilot`

Max pulse width decrement throttle from neutral to drive BearCar backward.

## `throttle_limit`

__Default Value:__ 0.35

__Pilot Modes:__ `teleop`, `autopilot`

From 0 (stop) to 1 (full throttle).
Speed cap for BearCar.

## `frame_rate`

__Default Value:__ 24

__Pilot Modes:__ `teleop`, `autopilot`

Camera frames per second

## `record_cap`

__Default Value:__ 15000

__Pilot Modes:__ `teleop`

Max number of data collection
