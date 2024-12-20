<h1 align="center">● INIT Build AI/ML Fall 2024</h1>

<p align="center">
    <!-- <a>Multi-Agent Reinforcement Learning for Traffic Optimization (SUMO-RL & PPO)</a> | <a>Parallel Robotics & Sim2Real Locomotion with Google Brax</a> -->
    <br>
</p>

![Init Build Presentation Cover (1)](https://github.com/user-attachments/assets/28a6b235-6bd6-4fc1-8c12-d3df3c5c6c1f)

<br>

## About

Our team developed and integrated cutting-edge Reinforcement Learning (RL) methodologies to address two primary challenges: optimizing traffic flow in urban environments and enabling sim2real locomotion in robotics. Utilizing frameworks such as **SUMO**, **SUMO-RL**, **Ray RLlib**, **Google Brax**, and **Proximal Policy Optimization (PPO)**, the projects aimed to deliver tangible improvements in real-world scenarios.

## Projects

### 1. Multi-Agent Traffic Optimization

<div align="center">
  <img src="https://github.com/user-attachments/assets/c5a89faf-a3dd-480e-ae77-2a50265550df" alt="Kapture GIF" width="45%" />
  <img src="https://github.com/user-attachments/assets/b0dda309-d5a5-4f1e-88f8-ea75c8787c60" alt="02 GIF" width="45%" />
</div>

**Objective**: Mitigate congestion and reduce wait times at a particularly busy and dangerous Miami intersection.

**Approach**:
- **Data & Simulation**: Leveraged **OpenStreetMap** to model the intersection and simulate peak traffic conditions using **SUMO**.
- **Reinforcement Learning Setup**: Framed traffic lights as RL agents within a **SUMO-RL** and **Ray RLlib** environment. The agents observed traffic density, queue lengths, and signal phases, adjusting signals at discrete time intervals.
- **Multi-Agent Coordination**: Employed a multi-agent RL framework, allowing each traffic light to make decisions that collectively optimized overall traffic flow.
- **Policy & Algorithm**: Implemented **PPO** for stable training, capable of handling multiple agents interacting simultaneously.

**Key Results**:
- Achieved up to a **90% reduction in average vehicular wait times** after 100,000 training steps, lowering delays to roughly one minute or under.
- Demonstrated the scalability and adaptability of RL policies to real-world intersections, improving traffic efficiency and safety.

### 2. Parallel Robotics & Sim2Real Locomotion

<div align="center">
    <img src="https://github.com/user-attachments/assets/cd79866a-fd30-4d75-a864-c7f08fa02b0b" alt="GIF 1" height="300px" />
    <img src="https://github.com/user-attachments/assets/45188ed5-c55f-46ee-b16e-d28b32d7b4ef" alt="GIF 2" height="300px" />
    <img src="https://github.com/user-attachments/assets/693b676f-4eee-4431-adf2-c1a1a43a648f" alt="GIF 3" height="300px" />
</div>

**Objective**: Enable robust sim2real transfer of learned locomotion policies for a custom-built hexapod robot.

**Approach**:
- **Simulation Environment**: Utilized **Google Brax**, a differentiable physics engine optimized for hardware acceleration, to train policies at scale.
- **Robot Modeling**: Defined the robot’s morphology using **MJCF**, capturing physical constraints and dynamics accurately.
- **Locomotion Training**: Conducted 100 million simulation steps, teaching the robot walking, running, and other advanced gaits through RL, again using **PPO**.
- **Sim2Real Transfer**: Successfully deployed the trained policies on a physical hexapod (controlled by a Raspberry Pi 4 Model B) with minimal adjustment, demonstrating high-fidelity transfer from simulation to the real world.

**Key Results**:
- Achieved stable and efficient locomotion in both simulation and hardware tests.
- Validated the effectiveness of differentiable physics-based simulation (Brax) in accelerating and improving RL training for complex robotics tasks.

## Technical Highlights

- **Multi-Agent Reinforcement Learning**: Incorporated frameworks like **SUMO-RL** and **Ray RLlib** to handle multiple agents (traffic lights), ensuring policies scaled effectively.
- **High-Fidelity Environments**: Used real-world data (OpenStreetMap for traffic; MJCF for robots) to ensure that models learned representations closely aligned with actual conditions.
- **Differentiable & Parallelized Training**: Leveraged **Brax** and **PPO** for highly parallelized, gradient-based optimization, reducing iteration time and improving policy quality.

---

### References

```bibtex
@misc{sumorl,
    author = {Lucas N. Alegre},
    title = {{SUMO-RL}},
    year = {2019},
    publisher = {GitHub},
    journal = {GitHub repository},
    howpublished = {\url{https://github.com/LucasAlegre/sumo-rl}},
}
@software{brax2021github,
  author = {C. Daniel Freeman and Erik Frey and Anton Raichuk and Sertan Girgin and Igor Mordatch and Olivier Bachem},
  title = {Brax - A Differentiable Physics Engine for Large Scale Rigid Body Simulation},
  url = {http://github.com/google/brax},
  version = {0.12.1},
  year = {2021},
}