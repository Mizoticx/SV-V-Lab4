
# Task 1 — Extract Requirements

# Autonomous Delivery Robot

| Req. ID | Requirement |
|---|---|
| R1 | The robot shall remain in the IDLE state when it is switched on and no delivery request is available. |
| R2 | The robot shall start navigation only after receiving a valid delivery request. |
| R3 | The robot shall navigate toward the requested destination while a delivery is active. |
| R4 | The robot shall continuously monitor its surroundings for obstacles during navigation. |
| R5 | When an obstacle is detected, the robot shall stop normal navigation and enter obstacle-avoidance mode. |
| R6 | After successfully avoiding an obstacle, the robot shall resume navigation toward the destination. |
| R7 | When the destination is reached, the robot shall start the package delivery process. |
| R8 | After successful delivery, the robot shall begin returning to the warehouse. |
| R9 | If the battery level becomes critically low during navigation, the robot shall stop the current journey and return to the warehouse. |
| R10 | When the robot reaches the warehouse, it shall become IDLE and wait for another delivery request. |

## Behavioral Restrictions

- The robot shall not transition directly from IDLE to DELIVERING.
- The robot shall not transition from AVOIDING_OBSTACLE directly to DELIVERING.
- The robot must receive a delivery request and navigate to the destination before delivery can begin.
