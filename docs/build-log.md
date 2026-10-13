
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

  
