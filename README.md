N-Body Gravity Simulator
Built by William Elgar Year 12 Physics, Mathematics & Computer Science

What is this project about?
This is a real-time gravitational simulator that models how multiple bodies 
interact under Newton's law of universal gravitation. My simulation also helps users to visualises 
orbital mechanics, chaotic trajectories and mathematical configurations 
including the figure-eight orbit and 2 body interactions. It was built entirely 
from scratch in Python as part of my application to study Physics at Imperial 
College London.

Physics Concepts considered in my project:
-Newton's Law of Universal Gravitation
-Every body attracts every other body with a force F = Gm₁m₂/r². This 
 simulator calculates these forces between every pair of bodies every frame.

The N-Body Problem
For three or more bodies, there was no exact mathematical solution that i could find therfore the 
only way to resolve this and make the model system function is through numerical simulation which i 
had found out through the use of in depth research through youtube and web pages.

Euler Integration vs Verlet Integration
I initially used the Euler integration method which calculates new positions 
using velocity at the start of each timestep. I observed orbital decay over 
long simulation times which is a wideley known limitation for simulations
caused by accumulated numerical errors as it only used the velocity at the 
very start of each timestep. I then upgraded to Verlet integration,
which uses the SUVAT equation s = ut + ½at² and averages old and new acceleration
for velocity updates. This dramatically improved the calculation stability.

The Softening Parameter
When two bodies get very close, the gravitational force approaches infinity 
— a singularity. I implemented a minimum distance check (softening parameter) 
used by real astrophysics simulators to prevent this.

Chaos Theory
The three-body problem exhibits sensitivity to initial conditions — tiny 
changes in starting position lead to completely different trajectories. This 
is a real example of chaos theory in action.

Features
- Real-time N-body gravitational simulation
- Verlet integration for accurate long-term orbital stability
- Live total energy display (kinetic + potential)
- Trail visualisation showing orbital paths
- Softening parameter to prevent numerical singularities
- Click anywhere on screen to add new bodies in real time
- Three preset scenarios:
  - Preset 1: Stable two-body orbit
  - Preset 2: Figure-of-eight orbit (Chenciner & Montgomery, 1993)
  - Preset 3: Three-body chaotic system

Preset Scenarios

Preset 1 — Two Body Orbit
Two equal masses orbit their common centre of mass in a stable elliptical orbit.

Preset 2 — Figure of Eight
A famous periodic solution to the three-body problem discovered by Chenciner 
and Montgomery in 1993. Three equal masses chase each other in a perfect 
figure-of-eight pattern. This requires extremely precise initial conditions 
and a small timestep to remain stable.

Preset 3 — Three Body Chaos
Three bodies with slightly asymmetric initial conditions producing unpredictable 
chaotic trajectories — a demonstration of the sensitivity of the three-body 
problem to initial conditions.

How to Run
Install dependencies:
pip install matplotlib

Run the simulator:
python "IMPORTANT IMPERIAL PHYSICS CODING N BODY PROJECT.py"

Then select a preset when prompted (1, 2 or 3) and click anywhere on the 
simulation window to add new bodies in real time.

What I Learned
Building this project taught me how real scientific simulations work — 
not just the physics equations, but the numerical methods used to approximate 
solutions that cannot be solved analytically. I learned why Euler integration 
fails for orbital mechanics, how Verlet integration conserves energy more 
accurately, and why the three-body problem has fascinated mathematicians for 
centuries.

Future Improvements
- Implement real astronomical units with actual planetary masses and distances
- Add collision detection and merging when bodies get too close
- Implement adaptive timestep that automatically reduces dt near close approaches
- Add a solar system preset using real NASA orbital data
- Explore other periodic three-body solutions beyond the figure of eight
