# PID Controller

This project was about using a Proportional–Integral–Derivative (PID) controller to drive a car around a simulator track. 

## Parameter Tuning

The final `(Kp,Ki,Kd)` values were `(0.18, 0.0005, 5)` 

The parameters were selected through trial and error combined with estimates of what the final error would be in the PID based on cross track error values returned by the simulator so that the PID error would fall within `[-1, 1]`

Started out by tuning only the `Kp` parameter so that it produced reasonable values of steering for cte values of upto 5. A final value of `0.18` was chosen for `Kp`

The car then started turning sufficiently for the curves, but it would oscillate a lot. To compensate, I started increasing the `Kd` value until the oscillation was reducted. Increasing the speed required increasing the `Kd` parameter as well. For `50mph` a `Kd` value of `5` produced reasonable driving

The car could drive around reasonably well without any `Ki` parameter. This is probably because there isn't a consistent bias in the system. Adding a minor `Ki` value of `0.0005` was sufficient

## Speed Control

The speed was controlled by using a PID controller for the throttle. The set speed was 50mph. The `p,i,d` values used were `(0.02, 0.0001, 0)`. Didn't attempt to tune the derivative control parameter since the speed remained reasonably stable around 50mph. 

The maximum speed attempted was 50mph. This is because there wasn't more time to tune the parameters for higher speeds. 

## Driving Video

Here's a [video of the PID controlling driving in the simulator](https://drive.google.com/open?id=0B2KVtEVE1lFjX1dDdDJxTkJaOUE)