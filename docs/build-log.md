
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
