# 云台-全向轮底盘机器人

## Demonstration videos

| Demonstration | Playback | Repository file |
| --- | --- | --- |
| Movement | [Watch video](https://jiraiyamr.github.io/assets/videos/omniwheel/movement.mp4) | [MP4](media/videos/movement.mp4) |
| Slope climbing | [Watch video](https://jiraiyamr.github.io/assets/videos/omniwheel/slope-climbing.mp4) | [MP4](media/videos/slope-climbing.mp4) |
| Shooting | [Watch video](https://jiraiyamr.github.io/assets/videos/omniwheel/shooting.mp4) | [MP4](media/videos/shooting.mp4) |

[View the project on my homepage](https://jiraiyamr.github.io/#projects).

## Gimbal-equipped four-omniwheel robot

Standalone robot project from Hexi Liu’s RoboMaster development portfolio. The project includes chassis and gimbal application code, robot-level command handling, and CAN-based board communication. The uploaded firmware remains an archived board/configuration snapshot.

**Platform:** STM32F407 · FreeRTOS/CMSIS-RTOS · CAN · UART · SPI  
**Project scope:** 云台-全向轮底盘机器人

## Control and integration

Four-wheel velocity mixing and motor-feedback PID control are present, together with yaw control, pitch motor commands, BMI088 sensing, and host communication. The four-omniwheel/O-layout platform identity follows the owner’s hardware identification and original archive name. The retained chassis mixing uses the same ±vx±vy+R·wz form as the mecanum snapshot (with a different rotational input sign); wheel mapping, orientation, geometric coefficients, and speed units must match the real chassis.

| Module | Start reading |
| --- | --- |
| Chassis kinematics and wheel-speed control | [chassis.c](firmware/Application/chassis.c) |
| Gimbal control | [gimbal.c](firmware/Application/gimbal.c) |
| Robot-level command handling | [robots.c](firmware/Robots/robots.c) |
| CAN board-to-board command transport | [Dual_board.c](firmware/modules/Dual_board/Dual_board.c) |
| CAN feedback and motor commands | [CAN_receive.c](firmware/modules/CAN_receive/CAN_receive.c) |
| Task creation | [freertos.c](firmware/Src/freertos.c) |
| Keil project | [C_Board_Standard_Robot.uvprojx](firmware/MDK-ARM/C_Board_Standard_Robot.uvprojx) |

## Supplied configuration

Enabled: INS, PC communication, and USB tasks. Chassis, gimbal, robot-command, shooting, and board-command sending task creation is commented out. This is an archived sensing/communication configuration within a robot project, rather than an enabled whole-robot build.

Code availability and task activation are documented separately. This repository does not claim that the archived startup configuration runs every robot subsystem simultaneously.

## Build and verification

Open the Keil project with ARMCC 5.06 update 5 (build 528) and the corresponding STM32F4 device pack. See [build notes](docs/build.md) and [configuration notes](docs/configuration.md).

Run `python tools/verify_import.py` to verify that the imported firmware bytes match the source manifest. This checks packaging integrity; compilation, flashing, and hardware behavior were not revalidated during the split.

## Evidence and contributions

- [Personal contribution record](docs/contributions.md)
- [Demonstration and testing](docs/evidence.md)
- [Source provenance](docs/provenance.md)
- [Third-party notices](THIRD_PARTY_NOTICES.md)

## Related robot projects

- [云台-麦克纳姆轮底盘机器人](https://github.com/JiraiyaMr/gimbal-mecanum-robot)
- [云台-全向轮底盘机器人](https://github.com/JiraiyaMr/gimbal-omniwheel-robot)
- [云台-舵轮底盘机器人](https://github.com/JiraiyaMr/gimbal-swerve-robot)

