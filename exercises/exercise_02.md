# Exercise 2: Actuating Our Model

**Actuation** is the process of breathing life into your robotic joints with the aid of motors, muscles, or anything else that causes controllable motion. Instead of falling under the influence of gravity, your robot will be able to hold a pose and change its shape on command by sending signals to the **actuators**, e.g. sending a sine wave to a BLDC motor.

To add actuators to our model, we first need to know which joints we want to be actuated. Sometimes, not all of them need their own motors. In this case, we are actuating `joint1` and `joint2`.

Between the actuator tags, add one motor for each joint:

```xml
<actuator>
    <position joint="joint1" ctrlrange="-1 1" kp="100" />
    <position joint="joint2" ctrlrange="-1 1" kp="100" />
</actuator>
```

A positive control value will make the joint spin counterclockwise, and a negative value will spin clockwise.

To test whether or not our motors work, you can add a slider to the right GUI pane for each motor using the following code:

```
idk
```
