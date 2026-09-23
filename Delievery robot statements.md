
# Task 2 — Identify States and Events/Conditions

## System States

| State ID | State Name | Description |
|---|---|---|
| S1 | IDLE | The robot is switched on, waiting for a delivery request. |
| S2 | NAVIGATING | The robot is moving toward the delivery destination. |
| S3 | AVOIDING_OBSTACLE | The robot has detected an obstacle and is avoiding it. |
| S4 | DELIVERING | The robot is delivering the package at the destination. |
| S5 | RETURNING | The robot is travelling back to the warehouse. |

## Events/Conditions

| Event ID | Event/Condition | Description |
|---|---|---|
| E1 | Delivery Request Received | A new delivery request is received. |
| E2 | Destination Reached | The robot arrives at the requested destination. |
| E3 | Delivery Successful | The package is successfully delivered. |
| E4 | Warehouse Reached | The robot arrives back at the warehouse. |
| E5 | Obstacle Detected | An obstacle is detected during navigation. |
| E6 | Obstacle Avoided | The obstacle has been successfully avoided. |
| E7 | Critical Battery | The battery level becomes critically low during navigation. |
