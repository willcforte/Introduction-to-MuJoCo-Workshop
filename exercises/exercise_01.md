# Exercise 1: Constructing the XML Model

To describe the hierarchical structure of a robot, MuJoCo uses XML, a markup language reminiscent of HTML that uses angular brackets to nest elements within each other. Here we will employ XML to create a two-joint robotic arm that can traverse a 2D space.

Note that, while building your model, it is helpful to load it into MuJoCo's realtime viewer so you can visualize the changes to your model as you make edits (use the `Reload` button on the left GUI pane under the `Simulation` tab).

The `<worldbody>` contains everything in our world. Within it, we can place invisible `<body>` elements.

In MuJoCo, a body can contain any of three things:

1. A `<geometry>`, i.e. the meshes that you can see
2. A `<joint>` which brings a degree of freedom to the body
3. A child `<body>`, e.g. the next joint in the arm

## First body

We want the first body to be rigidly connected to the ground, so it will not require a joint. Bodies by themselves do not take up space. To give them shape, we will add a geometry of type `cylinder` to ground our arm.

```xml
<worldbody>
    <body name="base" pos="0 0 0">
        <geom type="cylinder" size="0.05" rgba="0.7 0.2 0.2 1" />

    </body>
</worldbody>
```

## Second body

Now that we have the base of the robot made, we can form the first link of the arm with our second body.

Since we want this body to have one degree of freedom along the z-axis (vertical), we will add a `<joint>` in addition to our `<geom>`.

```xml
<worldbody>
    <body name="base" pos="0 0 0">
        <geom type="cylinder" size="0.05" rgba="0.7 0.2 0.2 1" />
        
        <body name="link1" pos="0 0 0">
            <joint name="joint1" type="hinge" axis="0 0 1" range="-180 180" />
            <geom type="capsule" fromto="0 0 0 0.3 0 0" size="0.03" rgba="0.2 0.2 0.7 1" />
            
        </body>
    </body>
</worldbody>
```

### Third body

The second link should be within `link1`. It will also have a joint and geometry of its own.

Final XML hierarchy:

```xml
<worldbody>
    <body name="base" pos="0 0 0">
        <geom type="sphere" size="0.05" rgba="0.7 0.2 0.2 1" />
        
        <body name="link1" pos="0 0 0">
            <joint name="joint1" type="hinge" axis="0 0 1" range="-180 180" />
            <geom type="capsule" fromto="0 0 0 0.3 0 0" size="0.03" rgba="0.2 0.2 0.7 1" />
            
            <body name="link2" pos="0.3 0 0">
                <joint name="joint2" type="hinge" axis="0 0 1" range="-180 180" />
                <geom type="capsule" fromto="0 0 0 0.3 0 0" size="0.03" rgba="0.2 0.7 0.2 1" />
            </body>
        </body>
    </body>
</worldbody>
```

Now that we have a physical model of our robot arm, we can proceed by equipping it with motors in **Exercise 2**.
