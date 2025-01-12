# Throw A Ball with More Functionalities

## Overview

This project, **Throw A Ball with More Functionalities**, explores physics-based animation using Unity to create realistic and interactive environments. It simulates dynamic interactions, such as a ball colliding with bricks and cloth, with added advanced functionalities like bouncing, shattering, and target tracking. The goal was to deepen our understanding of Unity's physics engine and apply physics principles to enhance virtual simulations commonly used in games.

### Features:
1. **Ball Throwing Mechanics**
   - User-controlled ball throwing with trajectory and speed based on input.
   - Dynamic bouncing off surfaces using Unity's physics materials.

2. **Brick Destruction**
   - Realistic shattering of bricks using the RayFire plugin for Unity.
   - Randomized fragmentation for unique destruction effects.

3. **Cloth Simulation**
   - Implemented cloth dynamics using two approaches:
     - Unity’s built-in cloth physics.
     - Custom Verlet integration for dynamic and interactive cloth behavior.

4. **Target Tracking and Obstacle Avoidance**
   - Homing missile-like tracking functionality for the ball.
   - The ball dynamically avoids obstacles and seeks a randomly moving target.

5. **Scene Switching and Reset**
   - Two distinct scenes: simple ball-brick collision and advanced tracking with obstacles.
   - Players can switch scenes by pressing **Space** and reset the game by pressing **R**.

---

## Implementation Details

### Ball Throwing Mechanics
- The ball is controlled using a custom **BallThrower** class, which handles:
  - Calculating throw speed and angle based on user input.
  - Applying physics forces using Unity’s `Rigidbody.AddForce` method.
  - Resetting the ball’s position and state for subsequent throws.

### Brick Destruction
- RayFire plugin was used to create realistic brick shattering effects.
- **Block.cs** script:
  - Attaches a RayFire rigid body to each brick.
  - Handles dynamic fragmentation upon collision.
  - Randomized parameters for fragmentation density ensure varied destruction effects.

### Cloth Simulation
- Two approaches were explored:
  1. **Unity’s Built-in Cloth Physics**: Utilized Unity’s cloth component for collision detection and deformation.
  2. **Custom Verlet Cloth Simulation**:
     - Implemented using a **ClothSimulator** class.
     - Created a particle-based grid with horizontal and vertical constraints.
     - Simulated particle movement using Verlet integration.
     - Resolved collisions between particles and the ball.

### Target Tracking and Obstacle Avoidance
- The tracking system was inspired by homing missile mechanics in games.
- **Missile.cs** script:
  - Continuously updates the ball’s direction using `Quaternion.Slerp` for smooth rotation.
  - Applies forward motion incrementally to simulate homing behavior.
  
- **Target.cs** script:
  - Randomly spawns a moving target and ensures it avoids obstacles using Unity’s `Physics.BoxCast`.
  - Guides the ball along an obstacle-free path by selecting clear trajectories.

---

## Results and Evaluation

### Sohail's Contribution:
- Implemented brick collision and destruction using Unity’s Rigidbody and Collider components.
- Developed ball throwing mechanics with adjustable speed and trajectory.
- Created two versions of cloth simulation: one using Unity’s physics and another using custom Verlet integration.
- Implemented collision detection for both cloth types.

### Baorong's Contribution:
- Enhanced the project with advanced functionalities:
  - Added bouncing effects using physics materials.
  - Developed realistic brick shattering with the RayFire tool.
  - Implemented ball tracking and obstacle avoidance using custom scripts.
  - Ensured seamless target movement and randomization in the scene.

### Performance
- The project achieved stable performance even with complex interactions and multiple dynamic objects.
- The shattering effects and cloth simulation added visual realism without significant performance degradation.

---

## Demo

### Video Demonstrations
- **Simple Scene (Ball-Brick Interaction)**: [Watch Demo](https://youtu.be/aEVTe9n-bgc)
- **Advanced Scene (Tracking & Obstacles)**: [Watch Demo](https://youtu.be/ACDKaYxJocY)

---

## Acknowledgements
- Special thanks to online tutorials, research papers, and discussion boards for providing valuable insights into Unity physics and animation techniques.
- Tools and resources used:
  - Unity Engine
  - RayFire plugin for realistic destruction
  - Research paper: "Animating Fracture" by James F. O'Brien & Jessica K. Hodgins ([arXiv link](https://arxiv.org/abs/example)).

---

## References
1. How to throw a ball – Unity Engine.
2. Throwing Objects – Unity Engine.
3. Throwing ball using AddForce – Unity Engine.
4. James F. O'Brien, Jessica K. Hodgins, "Animating Fracture", arXiv link.
5. How to throw a ball to a specific point on a plane? – Stack Overflow.

