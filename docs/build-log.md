
## Entry template (copy this for each day)

```
### YYYY-MM-DD (Day) — Short title
**Time spent:**
**Goal for today:**

**What I did**
-

**Problems**
- Symptom:
- How I figured out the cause:
- Fix:
- Result:

**Measurements**
| Thing | Value |
|---|---|
|  |  |

**What I learned**
-

**Photos / files**
- `images/YYYY-MM-DD_description.jpg`

**Next steps**
-
```

---

### 2026-10-08 (Thu) — Repo set up
**Goal for today:** Set up the GitHub repo and documentation structure before building anything, so the log starts from day one.

**What I did**
- Created the repo with folders for firmware, CAD, PCB, and docs.
- Wrote README skeleton, BOM template, and this log.

**Next steps**
- Decide degrees of freedom, arm lengths, and servos.
- Sketch the first version in CAD.
- 

### 2026-10-09 (Fri) — Testing gearboxes
**Goal for today:** learn about different types of gears and gearboxes

**What I did**
- used solidworks to design and 3d print a herringbone (double hylindrical) plantery gearbox
- had to print multiple because it was loose a lot
- 5 planets

**Next steps**
- calibrate the exact size and gera ratio

**Photos/files**
- 2026-10-09_herringbone-gearbox.webp

### 2026-10-010 (Sat)
**What I did**
- made a list of materials to purchase (motors, drivers, etc)

**Next steps**
- begin learning inverse kinemataics for 1 dof

  ### 2026-10-12 (Mon)
**What I did**
- Learned joint torque math (τ = F × r), sized for arm fully horizontal
- Calculated sample arm torques: shoulder ≈ 4.8 kg·cm, elbow ≈ 1.4 kg·cm
- Applied 2× safety factor vs. servo stall torque
- Learned ways to cut torque: light tip, motors at base, counterbalancing
- Learned gear ratio math (torque ×, speed ÷, P = τω)
- Compared spur, herringbone, belt, and worm drives
- Learned backlash (s = r × θ) and why the last stage matters most
- Reviewed R4 WiFi pins and buses (UART, I2C, SPI, CAN, PWM)

**Next steps**
- Run torque calcs on the real arm and pick motors
- Choose a transmission for each joint
- Learn dynamics (τ = Iα)
- Begin inverse kinematics for 1 DOF
- esp32 s3 pins

  ### 2026-10-13  (Tue)
**What I did**
- Learned why a NEMA 17 needs a driver (current, direction, inductive kickback)
- Compared A4988, DRV8825, and TMC2209 drivers
- Learned driver wiring: STEP/DIR/EN, VMOT, coil pairs, RESET to SLEEP
- Picked ESP32-S3 pins (STEP 39, DIR 40, EN 21) and which pins to avoid on the N16R8
- Learned the support parts: 100 µF VMOT cap, 10k EN pull-up, 3.3 V logic, common ground
- Learned to set current limit with Vref (torque ≈ current)
- Calculated microsteps and steps per degree with gearing
- Wrote arm_stepper_v1.ino (AccelStepper, joint angles in degrees)
- Learned how an H-bridge reverses current and why shoot-through is forbidden

**Next steps**
- Identify my driver and motor specs, then set Vref
- Wire one NEMA 17 and run arm_stepper_v1.ino
- Run torque calcs on the real arm and pick motors
- Choose a transmission for each joint
- Learn dynamics (τ = Iα)
- Begin inverse kinematics for 1 DOF

### 2026-10-14 (Wed)
**What I did**
- Learned mechanical advantage (MA = F_out ÷ F_in; force up, distance down)
- Finished Making Things Move Ch. 1 (simple machines) and took a practice test
- Finished Ch. 2 (materials) and took a practice test
- Learned stress, strain, stiffness vs. strength, and yield
- Calculated bending stress in printed links (σ = Mc/I): box section ≈ 1.4 MPa vs. flat bar ≈ 24 MPa
- Learned geometry beats material (stiffness grows with height³)
- Learned printed-arm failure points: creep, motor heat, layer lines, printed axles
- Chose filaments: PLA for prototypes, PETG for structural parts and motor mounts

  **Next steps**
- Read Ch. 3 (fastening and joining)
- Run stress/deflection calcs on the real link dimensions and motor weights
- Identify my driver and motor specs, then set Vref
- Wire one NEMA 17 and run arm_stepper_v1.ino
- Choose a transmission for each joint
- Learn dynamics (τ = Iα)
- Begin inverse kinematics for 1 DOF

  ### 2026-10-15 (Thu)
  **What I did**
- Finished Making Things Move Ch. 3 (fastening and joining) and took a practice test
- Covered thread sizes (M3 × 0.5 × 10), clearance vs. tap holes, and bolts vs. screws
- Covered vibration locking (nyloc nuts, threadlocker), washers, and press fits
- Covered shaft connections: set screws on D-shafts, clamping hubs, flexible couplers
- Covered heat-set inserts for printed parts and adhesives (strong in shear, weak in peel)
- Learned pivot joints should use steel shafts through bearings, not printed pins
- 
- **Next steps**
- Read the dynamics lesson (τ = Iα, inertia, motion profiles) and take its quiz
- Begin inverse kinematics for 1 DOF
- Run torque and stress calcs on the real arm's link lengths and motor weights
- Identify my driver and motor specs, then set Vref
- Wire one NEMA 17 and run arm_stepper_v1.ino
- Choose a transmission for each joint

### 2026-10-16 (Fri)
**What I did**
- Worked through the dynamics lesson: τ = Iα, degrees to radians, Iα vs. gravity torque
- Learned trapezoidal motion timing (t = v/a, θ = ½at², area under the speed graph)
- Learned reflected inertia (I ÷ N²) and the ~10:1 load-to-rotor inertia rule
- Learned holding vs. pull-out vs. detent torque
- Found papers on 5-DOF and low-cost 3D-printed arms to read

**Next steps**
- Take the dynamics quiz
- Read the high school 5-DOF manipulator paper
- Begin inverse kinematics for 1 DOF
- Run calcs on the real arm and pick motors and transmissions

### 2026-10-19 (Mon)
**What I did**
- Learned 5-DOF IK: base yaw, shoulder, elbow, wrist pitch, wrist roll
- Learned to split the problem: base yaw (atan2), then 2-link IK in the arm's vertical plane
- Learned to find the wrist center by stepping back from the tip along the approach angle φ
- Learned wrist pitch = φ − (θ1 + θ2)
- Worked example: block at (15, 10, 2) from above → base 33.69°, shoulder 41.35°, elbow −97.02°, wrist −34.33°
- Learned practical issues: unreachable approach angles, joint limits, roll alignment, base singularity, shoulder offset
- Wrote arm_ik5_v1.ino (5-DOF IK over Serial with limit and FK checks; AI-generated, logged)
- Combined both IK lessons into one page with an arm playground and a 5-DOF calculator

**Next steps**
- Run arm_ik_v1.ino and arm_ik5_v1.ino with my real link lengths and joint limits
- Take the IK and dynamics self-checks
- Combine IK with stepper code so the arm moves to a typed target
- Add homing with limit switches
- Pick a paper angle and draft a research question
- Run calcs on the real arm and pick motors and transmissions
