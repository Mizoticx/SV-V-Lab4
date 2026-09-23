# Task 5 — Verification Activity

## Autonomous Delivery Robot

This activity verifies whether the state transition table follows the behavioral requirements of the autonomous delivery robot.

---

## Check 1 — Invalid Transition

### Question

Can the following transition happen?

IDLE → DELIVERING

### Result

No, this transition is invalid.

### Violated Requirement

The robot must first receive a delivery request and navigate to the destination before starting the delivery process.

### Correct Transition Path

IDLE → NAVIGATING → DELIVERING

The robot must reach the destination before entering the DELIVERING state.

---

## Check 2 — Missing Transition

### Question

What happens if the robot moves from:

NAVIGATING → AVOIDING_OBSTACLE

but there is no transition back to NAVIGATING?

### Result

This creates a behavioral problem.

The robot would remain in the AVOIDING_OBSTACLE state and would not be able to continue its delivery journey toward the destination.

### Required Correction

The following transition must be included:

AVOIDING_OBSTACLE → NAVIGATING

### Condition

The transition occurs when the obstacle has been successfully avoided.

---

## Check 3 — Obstacle During Delivery

### Question

Can the robot move directly from:

AVOIDING_OBSTACLE → DELIVERING

### Result

No, this transition is invalid.

The robot must not enter the delivery process while it is dealing with an obstacle.

### Correct Transition Path

AVOIDING_OBSTACLE → NAVIGATING → DELIVERING

The robot must first return to NAVIGATING and reach the destination before entering DELIVERING.

---

## Verification Summary

| Verification Check | Result | Explanation |
|---|---|---|
| IDLE → DELIVERING | Invalid | A delivery request and navigation are required first. |
| Missing AVOIDING_OBSTACLE → NAVIGATING transition | Defect Found | The robot cannot continue its delivery journey after avoiding an obstacle. |
| AVOIDING_OBSTACLE → DELIVERING | Invalid | The robot must not deliver while handling an obstacle. |

## Final Conclusion

The state transition table must ensure that all valid transitions follow the stated behavioral requirements. Invalid transitions must be rejected, and every necessary transition must be included so that the robot can complete its delivery process safely and correctly.
