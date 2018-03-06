# FCND - Backyard Flyer Project

This code executes the following motion on the drone -
1. Drone takes off to an altitude of 3m
2. Drone follows a square trajectory
3. Drone lands at starting position

## Steps to run:
Run the following command after activating the fcnd python environment

```Python
python backyard_flyer.py
```

## Salient Points;

Getting the drone to execute the square trajectory was fairly simple. However, the drone always landed at a distance greater than the criteria from the global home.

The trick was to wait for the drone to settle (constraint on the velocity) before it lands.
 ```python
 if np.linalg.norm(self.local_velocity[0:2]) < 1.0:
    self.landing_transition()
 ```
