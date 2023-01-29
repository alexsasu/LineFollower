# LineFollower

### 🏁 ◼◼◼ 🏎

## About

Arduino two-person team project developed during a one-day hackathon, at the Introduction to Robotics course taken in the 3rd year at the Faculty of Mathematics and Computer Science, University of Bucharest. The project consisted of assembling and programming a line follower robot. 

The contributors of the project from this repository are me, along with [@andreipetrisor1999](https://github.com/andreipetrisor1999/LineFollower_ForkedBranch), and our team's name is Lightning McQueen ⚡🚗.

## Project Details

<details>
<summary><h2>Requirements 📋</h2></summary>

### Components Requirements

**Non-electronic:**
* 1 robot chassis
* 2 wheels
* 1 ball caster
* screws for the QTR-8A sensor
* zip ties (for keeping the components in place)

**Electronic:**
* 1 Arduino Uno
* 1 QTR-8A reflectance sensor
* 2 DC motors
* 1 L293D motor driver
* 1 LiPo battery (power source)
* 1 breadboard (medium; 400 pts)
* wires (per logic)

<details>
<summary><h4>Photo of the line follower kit with required components 📷</h4></summary>

![components requirementes](https://user-images.githubusercontent.com/87432371/215327213-3f86bc8e-b3b1-4039-8cee-ee41137acd52.png)

</details>

### Functionality Requirements

Assemble and program the makeshift car, so that it follows the racetrack consisting of a black line that loops, as fast and as correct (no shortcuts between parts of the track, no leaving the track, and no turning back on the track; the only allowed movement is the continuous movement along the black line) as possible. The QTR sensor should use only 6 of its sensors, and it should calibrate itself right before the robot starts traversing the track (meaning no manual calibration of the sensor; or, **as a bonus**, it could use calibration values stored in the EEPROM, from previous calibration attempts). By using a PID controller and modifying its gains (Kp, Ki (**optional**), Kd), define the characteristics of the robot's movement.

### Grading

In the range: 1 - 12p

By default: 1p

Calibration: 2.5p

Racetrack:
* \> 35s (but finished) -> 4.5p
* 35s ..... 5p
* 20s ..... 7.5p
* < 20s .... 7.5p

Bonus: 1p (LEDs for the robot, calibration values saved in EEPROM, robot cosmetics, etc)

</details>

<details>
<summary><h2>Functionality and Implementation Details 🎛</h2></summary>
</br>

**Functionality:**

At first, while on top of the black line, the robot calibrates its sensor by repeatedly moving left and right, learning this way to recognize the black line whenever it appears in front of the sensor, and to dismiss surfaces other than the black line. After a short period of calibration, the robot will attempt to follow any black surface in front of its sensor, while attempting to calculate its speed and to determine its movement behavior through the use of a PID controller.
> Note: Our team's robot managed to finish the racetrack showcased below in **15.430 seconds**!

**Implementation:**

The PID algorithm: The values for the PID controller were chosen randomly at first to observe the behaviour of the robot (not counting the I term and Ki gain). After many test drives during which we took an empirical approach, we settled with the gains Kp = 30, Ki = 0.08, Kd = 150, which pushed the robot close to its full potential. In the end, all of the PID controller's terms and gains were thoroughly used.

Calibration: We calibrated the robot by telling it to rapidly move left and right for a set period of time in the "setup" method of the code. Thus, we used the following self calibration method: when out of all the used sensors, only the rightmost sensor is on the black line, the robot will calibrate itself by turning to the right, when out of all the used sensors, only the leftmost sensor is on the black line, the robot will calibrate itself by turning to the left, and so on.

</details>

<details>
<summary><h2>Components Used ⚙</h2></summary>

**Non-electronic:**
* 1 robot chassis
* 2 wheels
* 1 ball caster
* screws for the QTR-8A sensor
* zip ties (for keeping the components in place)

**Electronic:**
* 1 Arduino Uno
* 1 QTR-8A reflectance sensor
* 2 DC motors
* 1 L293D motor driver
* 1 LiPo battery (power source)
* 1 breadboard (medium; 400 pts)
* wires (per logic)

</details>

<details>
<summary><h2>Showcase 🏎</h2></summary>
</br>

<details>
<summary><h4>Racetrack Picture:</h4></summary>

![racetrack](https://user-images.githubusercontent.com/87432371/213283226-c7c55969-2e19-4f83-b589-6c5681b6e521.jpeg)

</details>

<details>
<summary><h4>Robot Setup Pictures:</h4></summary>

![from the side](https://user-images.githubusercontent.com/87432371/213257714-dea2f7b3-b9df-413d-8651-d11315612f7a.jpeg)

![from the back](https://user-images.githubusercontent.com/87432371/213258241-515ff87a-385a-4171-9397-d99bdc7f5bd8.jpeg)

![from above](https://user-images.githubusercontent.com/87432371/213258269-01c975a0-e59b-475a-9e8f-da9e161ece65.jpeg)

![from the front](https://user-images.githubusercontent.com/87432371/213258303-9be18188-8e27-4d28-aa3b-0b191b589f92.jpeg)

</details>

**Robot Presentation 🤖:** https://www.youtube.com/watch?v=77cRA0fMZrk&ab_channel=AlexandruSasu

</details>
