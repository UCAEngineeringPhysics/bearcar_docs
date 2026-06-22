# Status Indicator

The RGB LED on the relay board reflects the BearCar's status.

## Red

`Error`, BearCar stops. No valid commands transmitted to Pico.

## Cyan

`Standby`, BearCar stops. Communication between RPi and Pico not established yet.

## Yellow

`Pause`, BearCar stops. Pico hears commands from RPi but won't respond to them.

## Green

`Normal`, BearCar moves under the joysticks' control.

## Blue

`Recording`, BearCar moves, and data recording is activated

## Purple

`Autonomous`, BearCar moves under the autopilot's control.

## OFF

Pico is not running. Check if proper code is on duty.
