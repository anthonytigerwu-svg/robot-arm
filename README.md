# Robot Arm

> A 3D-printed desktop robot arm built from scratch: custom CAD, custom electronics, custom firmware.

![Robot arm hero photo](docs/images/hero.jpg)
<!-- Replace with a photo of the finished arm once you have one. -->

**Status:** 🚧 In progress (started October 2026)

## Why I built this

_One or two sentences on the problem or goal. Example: "I wanted to learn how real robotic arms turn a target position into joint angles, so I designed one from scratch instead of buying a kit."_

## Specs

| | |
|---|---|
| Degrees of freedom | _e.g. 4 (base, shoulder, elbow, gripper)_ |
| Reach | _e.g. ~220 mm_ |
| Payload | _e.g. 50 g target_ |
| Positioning accuracy | _e.g. ±5 mm target (measured: TBD)_ |
| Controller | _e.g. Arduino UNO R4 WiFi_ |
| Actuators | _e.g. MG996R / SG90 servos_ |
| Power | _e.g. separate 5 V 3 A supply for servos_ |
| Material | _e.g. PLA_ |

## How it works

_Add a block diagram here once the design settles, e.g.:_

```
Laptop (serial commands) → Microcontroller → Servo signals → Joints
                                   ↑
                         5 V servo supply (shared ground)
```

_Explain in a short paragraph how a command turns into motion._

## Design decisions

_The interesting choices and why you made them. Examples:_
- _Why these servos and not steppers_
- _Arm segment lengths and how you chose them_
- _Print orientation for strength at the joints_

## Results

_Measured performance, photos and videos of it working. Fill in as you go._

## Problems & what I learned

_The biggest problems you hit and how you solved them. Pull the best ones from the [build log](docs/build-log.md)._

## Build it yourself

- **Parts:** see [BOM.md](BOM.md)
- **CAD files:** [`cad/`](cad/)
- **Electronics:** [`pcb/`](pcb/)
- **Firmware:** [`firmware/`](firmware/)

## Repo layout

```
robot-arm/
├── README.md        ← you are here
├── BOM.md           ← parts list
├── firmware/        ← Arduino code
├── cad/             ← STEP files + link to CAD source
├── pcb/             ← KiCad project, schematic PDF, Gerbers
└── docs/
    ├── build-log.md ← dated development log
    └── images/      ← photos and diagrams
```
