# Archived configuration

Enabled: INS, PC communication, and USB tasks. Chassis, gimbal, robot-command, shooting, and board-command sending task creation is commented out. This is an archived sensing/communication configuration within a robot project, rather than an enabled whole-robot build.

Four-wheel velocity mixing and motor-feedback PID control are present, together with yaw control, pitch motor commands, BMI088 sensing, and host communication. The four-omniwheel/O-layout platform identity follows the owner’s hardware identification and original archive name. The retained chassis mixing uses the same ±vx±vy+R·wz form as the mecanum snapshot (with a different rotational input sign); wheel mapping, orientation, geometric coefficients, and speed units must match the real chassis.

All three robot projects retain a shared framework. The existence of additional chassis/steering code in a snapshot does not prove that every variant is configured or used on this robot.
