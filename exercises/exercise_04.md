# Exercise 3: Python Simulation

In order to do the mathematical operations required to control our robotic arm, we will use our XML model alongside MuJoCo's Python library. Start with `2R_robotic_arm.py` in the `exercises` folder.

You'll notice that we start by importing our XML file:

```python
# Load our XML model
model = mujoco.MjModel.from_xml_path("2R_robotic_arm.xml")
data = mujoco.MjData(model)
```

There is then a function to generate a control signal from a PID controller.

INSTRUCTIONS WORK IN PROGRESS
