[[1,1 - Control Systems for Movement]] $\leftarrow$ Back

---
# CSR for Autonomous Mobile Robots

#### 1) Multiple Goals
Robot may have multiple goals
- Some of these goals may be conflicting.
- Some of these goals may be more important than others (avoid car on a collision course vs arrive at destination).

Additionally, control systems MUST be responsive to high priority level goals whilst still paying attention to low level goals.
- Whilst avoiding car on a collision course, balance of chassis must be maintained.

#### 2) Multiple Sensors
Robots most likely have multiple sensors.
- All sensors have an error in their readings.
- No direct, analysable mapping from sensor readings to desired physical quantities exist. Some processing ALWAYS has to be done.
- Sensors may also give inconsistent readings
	- May be due to error.
	- May be due to environmental conditions impacting the sensors.

DESPITE all of this, robot's control system must still make decisions under these conditions.

#### 3) Robustness
Robot MUST be robust.
- When some sensors fail, robot should be able to adapt and cope with remaining functional sensors.
- When environment changes, robot's control system should still achieve a level of sensible, rational behaviour.
- Robot should still be able to function to some degree if there are some faults in it's processors.

#### 4) Additivity
As more sensors and capabilities added, robot requires more processing power.
- If more processing power isn't added, the original capabilities of robot will be reduced.