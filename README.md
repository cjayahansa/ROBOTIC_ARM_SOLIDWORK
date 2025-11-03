# 4DOF Robotic Arm — SolidWorks Project

**Author:** Chamindu Jayahansa

**Field:** Robotic Engineering

**Project Status:** Prototype / Design (SolidWorks)

---

## Overview

This repository contains the SolidWorks design and documentation for a 4‑degree‑of‑freedom (4DOF) robotic arm. The project demonstrates fundamental robotic kinematics and mechanical design principles suitable for undergraduate study and early‑stage research in robotic engineering. The model is intended for CAD validation, motion study, and as a starting point for control and embedded integration.

## Key Features

* 4 DOF articulated manipulator: base rotation, shoulder, elbow, and wrist pitch.
* Modular link and joint design for easy modification and component replacement.
* Parametric sketches and mates for quick geometry updates.
* Assembly configured for motion study and basic collision checks.
* Exportable parts for 3D printing and prototyping.

## Specifications

* Degrees of Freedom: 4 (Base yaw, Shoulder pitch, Elbow pitch, Wrist pitch)
* Working envelope: *see SolidWorks motion study / README diagrams* (configure per link lengths)
* Typical actuator size: N20 / 25 / 37 class DC motors or hobby servos (specify in BOM)
* Materials: PLA (prototype), Aluminum (final design), Steel fasteners

## Repository Structure

```
/ (root)
├─ CAD/                    # SolidWorks part and assembly files (.sldprt, .sldasm)
├─ Drawings/               # 2D drawings and fabrication drawings
├─ BOM/                    # Bill of Materials (CSV / XLSX)
├─ MotionStudies/          # SolidWorks motion study files and exports
├─ Exports/                # STL, STEP, and parasolid exports
├─ Docs/                   # This README and additional documentation
└─ Images/                 # Screenshots and rendered images
```

## Bill of Materials (example)

| Item              | Description                           | Quantity  | Notes                 |
| ----------------- | ------------------------------------- | --------- | --------------------- |
| Base plate        | 120 x 120 mm aluminum plate           | 1         | Custom cut            |
| Link 1 (shoulder) | Printed PLA part or machined aluminum | 1         | Parametric sketch     |
| Link 2 (forearm)  | Printed PLA part or machined aluminum | 1         |                       |
| Motor - shoulder  | DC gearmotor / servo                  | 1         | Specify torque rating |
| Motor - elbow     | DC gearmotor / servo                  | 1         |                       |
| Motor - wrist     | DC gearmotor / servo                  | 1         |                       |
| Motor - base      | Rotary actuator / stepper             | 1         |                       |
| Fasteners         | M3, M4 screws, nuts, washers          | as needed |                       |

> Replace the example items above with your actual components and specifications.

## Assembly Instructions

1. Open the assembly file `CAD/4DOF_Arm.sldasm` in SolidWorks.
2. Ensure the `CAD/` folder contains all referenced part files. Use `File → Find References` if any links are missing.
3. Mate parts in the following order: base plate → base joint → shoulder link → elbow link → wrist link → end effector.
4. Verify motor interfaces and mounting holes — adjust the `Config` table if you have different motor footprints.

## Motion Study & Kinematics

* Use **Motion Study** in SolidWorks to simulate joint motion. Create keyframes for each joint rotation and run the animation to verify reach and collisions.
* For preliminary kinematic verification, export joint angles over time and compute forward kinematics externally (e.g., Python / MATLAB) if required.

## Exporting for Prototyping

* To export parts for 3D printing: `File → Save As → STL` on each part. Check orientation and add print supports as needed.
* For interoperability with other CAD tools: export STEP (`.step` / `.stp`) or Parasolid (`.x_t`).

## Tips & Good Practices

* Keep sketches fully defined and use global variables (skeleton sketch or Equations) to manage link lengths and offsets.
* Use `SpeedPak`/`Large Assembly` mode if the assembly becomes slow.
* Add cosmetic threads only when needed; avoid excessive detail in prototype exports.
* Keep a separate configuration for `Prototype` (lightweight) and `Manufacturing` (detailed) versions.

## Screenshots / Renders
![IMAGE 1](https://github.com/cjayahansa/ROBOTIC_ARM_SOLIDWORK/blob/main/Screenshot%202025-10-19%20194633.png)
![IMAGE 1](https://github.com/cjayahansa/ROBOTIC_ARM_SOLIDWORK/blob/main/Screenshot%202025-10-19%20194733.png)
![IMAGE 1](https://github.com/cjayahansa/ROBOTIC_ARM_SOLIDWORK/blob/main/Screenshot%202025-10-19%20194858.png)

## Known Issues

* Collision checks may be optimistic if motors, wiring, and connectors are not modeled.
* Tolerances for press‑fits and mounts are not finalized — verify with hardware before assembly.

## Next Steps / Roadmap

* Add sensor mounts (force, IMU, encoders).
* Integrate motor controller and wiring harness models.
* Prepare controller code (ROS node or microcontroller firmware) and example trajectory scripts.
* Create manufacturing drawings with tolerances for critical mating surfaces.

## Contact

**Author:** Chamindu Jayahansa

**Field:** Robotic Engineering

**Email / Contact:** (chaminduliyangam1761@gmail.com)

---

