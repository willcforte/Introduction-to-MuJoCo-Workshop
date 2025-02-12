# Exercise 4: Positional Control

PID control is a classical control method that takes three considerations into account:

1. How far away are you from your target?
2. Are you moving towards your target?
3. How long have you been away from your target?

The sum of these considerations will result in an integer that influences the acceleration provided by the motor.

The P term stands for "proportional". If the error is larger, the corrective forces should be larger, and vice versa.

The D term stands for "derivative". If you are moving away from your target, additional force is required to change direction. If you are already moving towards your target, it is possible that no changes are needed.

The I term stands for "integral". While P & D could control things decently well by themselves (a "PD controller"), the integral term is a perfectionist that helps you get the error down to the lowest possible value.
