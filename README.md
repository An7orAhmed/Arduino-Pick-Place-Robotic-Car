```markdown
# Arduino Pick & Place Robotic Car

A robotic vehicle with object manipulation capabilities, controlled via Bluetooth/serial interface.

## Description
This project implements a mobile robotic car with a servo-controlled gripper arm for pick-and-place operations. The system supports bidirectional motor control for movement (forward/backward/left/right) and precision servo adjustments for lifting/lowering (servo1) and opening/closing (servo2) the gripper. Control is enabled through both serial monitor and Bluetooth communication.

## Key Features
- Bidirectional DC motor movement control
- Adjustable servo arm with 5° resolution
- Dual control interfaces: 
  - Bluetooth (HC-05/HC-06 module)
  - Serial monitor
- PWM-enabled motor speed control
- Safety limits for servo angles (1-100° for vertical arm, 1-90° for gripper)

## Pin Mapping
| Component       | Arduino Pin |
|-----------------|-------------|
| Motor Driver PWM | 12         |
| Motor1 A/B       | 9/8        |
| Motor2 A/B       | 11/10      |
| Servo1 (Vertical)| 6          |
| Servo2 (Gripper) | 7          |
| Bluetooth RX/TX  | 3/4        |

*Note: Diagram connections in `/blobk.pdf` may require verification against actual implementation.*

## Control Commands
| Command | Action             |
|---------|--------------------|
| F       | Move Forward       |
| B       | Move Backward      |
| L/R     | Turn Left/Right    |
| S       | Full Stop          |
| V/v     | Raise/Lower Arm    |
| X/x     | Open/Close Gripper |

## Resources
[System Block Diagram](https://drive.google.com/file/d/1-block.pdf/view) (Google Drive link)

> **Implementation Note**: Servo motion uses 10ms delay increments between 5° position changes for mechanical stability. Motor control logic includes instant braking on stop commands.
```