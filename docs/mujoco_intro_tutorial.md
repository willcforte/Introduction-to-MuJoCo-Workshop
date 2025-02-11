# Workshop Script: Introduction to the MuJoCo Simulator

## About Me

My name's Will, and I am an undergraduate freshman in the Engineering Honors Academy and aspiring robotics researcher. I'm really excited to be hosting my first workshop here at N2E Robotics. You can check out my personal website, willcforte.com, where I post my personal projects.

I'm currently interning in Prof. Jingang Yi's lab, working on the mechanical design of our new bipedal robot. I also really like robotic simulations, for a few reasons that I'll get to shortly.

So, first of all, what is MuJoCo?

## What is MuJoCo?

MuJoCo is an open-source physics simulator developed by Yuval Tassa and Emo Todorov, researchers from the University of Washington. It's now maintained by Google DeepMind, and it is used extensively in current robotics research.

It's simple, intuitive, and--in my opinion--pretty fun to mess around with to see your robots come to life.

## DIY 12-Motor Quadruped

But let me tell you about my own experiences with MuJoCo.

During the summer after my junior year of high school, I borrowed a bunch of motors from my FTC robotics teacher with the goal of creating a fully-actuated quadruped.

## MuJoCo Simulation

I wanted to control the thing, so I then created a digital model of this robot within MuJoCo so that I could visualize the current state and also use the model to predict what would happen in real life.

If there were any large torques applied to the joints--the design was very poor, but that's besides the point--I'd be able to see this in simulation and take steps to mitigate it in real life.

You can imagine that such a system allows someone more capable than I to realistically predict what may actually happen to the simulation and anticipate real-world events.

So this brings me to some reasons:

## Why Simulate

First of all, robots--especially the cool ones--are all super expensive. I don't have $6000 to drop on buying the parts for an Open Robotics biped, setting up a stand in my dorm room, and being the reason for an oddly-specific Rutgers housing policy.

Everyone loves breaking things, but we don't have to suffer any consequences

It's way easier than a real experiment. In the lab, we need two people for the robot. One hovers over the emergency stop, one holds the robot's harness and pulls up when the robot trips so it doesn't hurt itself. Now do this 100,000 times to train our reinforcement learning policy.

Accurate sensors--we can cheat by beaming super-accurate data straight to the robot instead of worrying about noise, but you can also add artificial inaccuracies if you really hate yourself.

And, the most important one. There is a certain dullness that is associated with computer programming--you type (or more realistically ask ChatGPT), a string comes out, success. But when something you've designed in CAD actually moves in front of you, it's really fulfilling, and this is the magic of simulation that I want to share with you guys today.

## Our Objective

Today, I will show you how to make what's called a "2R manipulator". Basically, just 2 revolute joints (shout out to Onur Bilgen in statics) that are combined to make an arm that can a certain space of points within 2D.

There's gonna be two joints, theta_1 and theta_2. Each joint is going to have two attributes: a position and velocity. This makes 4 variables, which will constitute our state vector x. x will tell us where the system is and what it's doing.

There's a point on the end of the arm we call the "end effector", and this is really the point of interest for us. We don't care about do this angle or that, we care about, "Robot, please go here and do something." So all of those angles will be taken care of with our code.

## Download MuJoCo

So, to get into the magical simulated realm, you'll first need to head over to mujoco.org, click Download, and let's choose v3.2.7. I thought that this was Linux-only, but it turns out that I was just using a weird version, so Windows and Mac users may proceed.

## Simulation Environment

Once MuJoCo has been installed, we can go ahead and test out our environment by running `simulate.sh`.

It will prompt us to drag-and-drpop an XML file. This XML will basically describe where the arms and joints of the robots are.

## 



## MuJoCo Simulation

MuJoCo is an open source physics simulator developed by Google DeepMind.

