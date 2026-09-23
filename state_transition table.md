
# Task 3 — State Transition Table and Verification

## State Transition Table

| Current State | Event/Condition | Next State | Expected Behavior |
|---|---|---|---|
| IDLE | Delivery Request Received | NAVIGATING | Start travelling toward the destination. |
| NAVIGATING | Obstacle Detected | AVOIDING_OBSTACLE | Stop normal navigation and avoid the obstacle. |
| AVOIDING_OBSTACLE | Obstacle Avoided | NAVIGATING | Resume travelling toward the destination. |
| NAVIGATING | Destination Reached | DELIVERING | Start the package delivery process. |
| DELIVERING | Delivery Successful | RETURNING | Begin the journey back to the warehouse. |
| NAVIGATING | Critical Battery | RETURNING | Stop the current delivery journey and return to the warehouse. |
| RETURNING | Warehouse Reached | IDLE | Become idle and wait for another delivery request. |

## Verification Activity

### Check 1 — Invalid Transition

**Invalid transition:** IDLE → DELIVERING

This transition must not be allowed.

**Violated requirement:** The robot must first receive a delivery request and navigate to the destination before entering the delivery process.

### Check 2 — Missing Transition

Consider the following sequence:

NAVIGATING → AVOIDING_OBSTACLE

If there is no transition from AVOIDING_OBSTACLE back to NAVIGATING, the robot cannot resume its journey toward the destination.

**Result:** The robot cannot complete the delivery because the transition triggered by Obstacle Avoided is missing.

**Required transition:**

AVOIDING_OBSTACLE → NAVIGATING

### Check 3 — Obstacle During Delivery

The transition AVOIDING_OBSTACLE → DELIVERING must not be allowed.

The robot can enter DELIVERING only after reaching the destination from NAVIGATING. If the robot is dealing with an obstacle, it must first return to NAVIGATING and continue toward the destination.

## Verification Summary

| Verification Check | Expected Result |
|---|---|
| IDLE → DELIVERING | Rejected because it violates the required delivery sequence. |
| Missing AVOIDING_OBSTACLE → NAVIGATING transition | Identified as a defect because the robot cannot resume navigation. |
| AVOIDING_OBSTACLE → DELIVERING | Rejected because delivery cannot begin while obstacle avoidance is active. |

## Suggested Git Commit Messages

1. Extract delivery robot requirements
2. Create state and event list
3. Create state transition table
4. Verify transitions against requirements
