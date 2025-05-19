# Ray-Quasar Racing
Ray-Quasar has developed a novel autonomous racing algorithm atop a one-tenth scale car. Our team has synthesized LiDAR sensing and simple kinematics to create a reliable and fast logic for the optimal navigation of any race environment.

We employ a two-fold approach:
A purely reactive disparity-extension algorithm commands the initial scouting stage. The car tears through the track, seemingly on pure instinct, and maps the walls as it goes, keeping track of where it has itself traveled (localization). The LiDAR sensor uses lasers and infrared sensors to map a planar slice of its surroundings, offering near real-time distances to walls and obstacles 360° around the car. By relating the image of our surroundings to the vehicle’s velocity, we create a map.

After this first lap, we use model-predictive control to generate increasingly faster racelines through the mapped track to shave off every extra second.
Vehicle management is done via ROS 2 Humble, a real-time robotics framework on the NVIDIA Jetson Orin Nano DK. The car itself is an adapted Traxxas RC car with a Vedder ESC, capable of great speeds without sacrificing control. In true racing fashion, we have modified our chassis and mounting systems for the utmost sleekness and serviceability; we are not just a race car, we are a racing program.

## How to Use:

### Prerequisites: 
* ROS2 Humble installed on Ubuntu 22.04 (All work was done on NVIDIA Jetson Orin Nano, Jetpack 6) 
* A control laptop with SSH keys and agent working
* Hardware specific packages will require:
  * Trampa VESC 6 Mk6 (See VESC section)
  * Traxxas Velineon 3500 3351R BLDC Motor (See motor configuration section)
  * Xbox One Controller (See `teleop_tools` section)
  * RPLidar A3 (see LiDAR section)
