# Introduction to the MuJoCo Simulator Workshop

This repository contains the presentation and files to accompany a workshop held at the Rutgers N2E Robotics club on February 11th, 2025.

The `docs` folder contains a PDF copy of the presentation.

If you want to follow along with the workshop, read the Markdown guides and use the files provided in the `exercises` directory.

To see the final demos from this workshop, go to the `reference` directory.

## Exercises

1. [Constructing the XML Model](./exercises/exercise_01.md)
2. [Actuating Our Model with Positional Servos](./exercises/exercise_02.md)
3. 2. [Actuating Our Model with Motors](./exercises/exercise_03.md)
4. [Using MuJoCo with Python](./exercises/exercise_04.md)
5. [PID Control of Positional Trajectory](./exercises/exercise_05.md)
6. [PID Control of Motor Trajectory](./exercises/exercise_06.md)

## Running the Reference Code

The reference will automatically display a graph of the angular oscillations against the desired signals after 500 simulation timestamps (should take roughly 1 minute) to help during PID tuning.

[Run Motor PID Demo](./reference/motor_demo.md)

[Run Positional Servo PID Demo](./reference/position_demo.md)
