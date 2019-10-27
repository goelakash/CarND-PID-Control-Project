# Write-up
--------

## Summary:
The project implements a PID controller to calculate the control signals for steering angle and the speed of the autonomous vehicle in realtime.
The tuning was done manually. The car achieved max speeds of 70mph around the track.

## PID Steering:
----------------

1. Started with a simple PID with Kp value of 1.0 and 0.0 for the rest. The throttle was kept at a constant value of 0.4.
2. This caused the car to veer off quickly off track, so gradually reduced it to 0.1, then 0.05. The car remained on track then.
3. On the corners, the car stepped of the lanes, so added a differential co-efficient Kd equal to 1.0.
4. Tuned this to higher to 2.0, then 3.0. But thise increased jerkiness of the motions, the parameter was left at 2.5.
5. At a sharp corner, the car still went off the lanes. So the Ki paramter was set as 0.01 and tuned to a lower value of 0.003 to make sure car stayed in track.

## PID Speed:
----------------

1. For speed, it is logical to assume that the higher the steering angle deviation, lower the speed should be.
2. Started with 1.0, 0.0 and 0.0 values for the Kp, Ki and Kd params of the PID.
3. The throttle threshold was kept at a lower value of 0.05 and an upper value of 0.9. This was done to make sure that the car doesn't stop completely and also doesn't get very fast and leave the lanes.
4. Increased the Kp value until the car was kept stable around 2.5.
5. No tuning done for other parameters.