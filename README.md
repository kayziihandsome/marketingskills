# ROS2 Dobot – Read & Write Interface

Node: `/dobot_bringup_ros2`

---

## I. READ – Thông tin có thể đọc từ robot

## 1. Trạng thái robot (Topics)

### /joint_states_robot
**Type:** `sensor_msgs/msg/JointState`

```
# This is a message that holds data to describe the state of a set of torque controlled joints.
#
# The state of each joint (revolute or prismatic) is defined by:
#  * the position of the joint (rad or m),
#  * the velocity of the joint (rad/s or m/s) and
#  * the effort that is applied in the joint (Nm or N).
#
# Each joint is uniquely identified by its name
# The header specifies the time at which the joint states were recorded. All the joint states
# in one message have to be recorded at the same time.
#
# This message consists of a multiple arrays, one for each part of the joint state.
# The goal is to make each of the fields optional. When e.g. your joints have no
# effort associated with them, you can leave the effort array empty.
#
# All arrays in this message should have the same size, or be empty.
# This is the only way to uniquely associate the joint name with the correct
# states.

std_msgs/Header header
	builtin_interfaces/Time stamp
		int32 sec
		uint32 nanosec
	string frame_id

string[] name
float64[] position
float64[] velocity
float64[] effort
```

### /dobot_msgs_v4/msg/ToolVectorActual
**Type:** `dobot_msgs_v4/msg/ToolVectorActual`

```
float64 x
float64 y
float64 z
float64 rx
float64 ry
float64 rz
```

### /dobot_msgs_v4/msg/RobotStatus
**Type:** `dobot_msgs_v4/msg/RobotStatus`

```
float64 x
float64 y
float64 z
float64 rx
float64 ry
float64 rz
```

## 2. Trạng thái robot (Services – Read)

### /dobot_bringup_ros2/srv/AI
**Type:** `dobot_msgs_v4/srv/AI`

```
int32 index
---
int32 res
```

### /dobot_bringup_ros2/srv/DI
**Type:** `dobot_msgs_v4/srv/DI`

```
int32 index
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/DIGroup
**Type:** `dobot_msgs_v4/srv/DIGroup`

```
int32[] args
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetAO
**Type:** `dobot_msgs_v4/srv/GetAO`

```
int32 index
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetAngle
**Type:** `dobot_msgs_v4/srv/GetAngle`

```
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetCoils
**Type:** `dobot_msgs_v4/srv/GetCoils`

```
int32 index
int32 addr
int32 count
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetCurrentCommandId
**Type:** `dobot_msgs_v4/srv/GetCurrentCommandId`

```
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetDO
**Type:** `dobot_msgs_v4/srv/GetDO`

```
int32 index
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetDOGroup
**Type:** `dobot_msgs_v4/srv/GetDOGroup`

```
int32[] index_group
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetErrorID
**Type:** `dobot_msgs_v4/srv/GetErrorID`

```
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetHoldRegs
**Type:** `dobot_msgs_v4/srv/GetHoldRegs`

```
int32  index
int32  addr
int32  count
string val_type
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetInBits
**Type:** `dobot_msgs_v4/srv/GetInBits`

```
int32 index
int32 addr
int32 count
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetInRegs
**Type:** `dobot_msgs_v4/srv/GetInRegs`

```
int32   index
int32   addr
int32   count
string  val_type
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetInputBool
**Type:** `dobot_msgs_v4/srv/GetInputBool`

```
int32 address
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetInputFloat
**Type:** `dobot_msgs_v4/srv/GetInputFloat`

```
int32 address
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetInputInt
**Type:** `dobot_msgs_v4/srv/GetInputInt`

```
int32 address
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetOutputBool
**Type:** `dobot_msgs_v4/srv/GetOutputBool`

```
int32 address
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetOutputFloat
**Type:** `dobot_msgs_v4/srv/GetOutputFloat`

```
int32 address
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetOutputInt
**Type:** `dobot_msgs_v4/srv/GetOutputInt`

```
int32 address
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetPose
**Type:** `dobot_msgs_v4/srv/GetPose`

```
int32 user
int32 tool
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/GetStartPose
**Type:** `dobot_msgs_v4/srv/GetStartPose`

```
string trace_name
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/InverseKin
**Type:** `dobot_msgs_v4/srv/InverseKin`

```
float64 x
float64 y
float64 z
float64 rx
float64 ry
float64 rz
string  use_joint_near
string  joint_near
string  user
string  tool
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/PositiveKin
**Type:** `dobot_msgs_v4/srv/PositiveKin`

```
float64  j1
float64  j2
float64  j3
float64  j4
float64  j5
float64  j6
string   user
string   tool
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/RobotMode
**Type:** `dobot_msgs_v4/srv/RobotMode`

```
---
string robot_return
int32 res
```

## II. WRITE – Các lệnh ghi / điều khiển robot

## 1. Power / Enable / Safety

### /dobot_bringup_ros2/srv/PowerOn
**Type:** `dobot_msgs_v4/srv/PowerOn`

```
---
int32 res
```

### /dobot_bringup_ros2/srv/EnableRobot
**Type:** `dobot_msgs_v4/srv/EnableRobot`

```
---
int32 res
```

### /dobot_bringup_ros2/srv/DisableRobot
**Type:** `dobot_msgs_v4/srv/DisableRobot`

```
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/ClearError
**Type:** `dobot_msgs_v4/srv/ClearError`

```
---
int32 res
```

### /dobot_bringup_ros2/srv/EmergencyStop
**Type:** `dobot_msgs_v4/srv/EmergencyStop`

```
int32 value
---
int32 res
```

### /dobot_bringup_ros2/srv/Stop
**Type:** `dobot_msgs_v4/srv/Stop`

```
---
int32 res
```

### /dobot_bringup_ros2/srv/Pause
**Type:** `dobot_msgs_v4/srv/Pause`

```

---
int32 res
```

## 2. Motion

### /dobot_bringup_ros2/srv/MovJ
**Type:** `dobot_msgs_v4/srv/MovJ`

```
bool mode
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] param_value
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/MovJIO
**Type:** `dobot_msgs_v4/srv/MovJIO`

```
bool mode
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] mdis
string[] param_value
---
int32 res
```

### /dobot_bringup_ros2/srv/MovL
**Type:** `dobot_msgs_v4/srv/MovL`

```
bool mode
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] param_value
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/MovLIO
**Type:** `dobot_msgs_v4/srv/MovLIO`

```
bool mode
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] mdis
string[] param_value
---
int32 res
```

### /dobot_bringup_ros2/srv/MoveJog
**Type:** `dobot_msgs_v4/srv/MoveJog`

```
string axis_id
string[] param_value
---
int32 res
```

### /dobot_bringup_ros2/srv/StopMoveJog
**Type:** `dobot_msgs_v4/srv/StopMoveJog`

```
---
int32 res
```

### /dobot_bringup_ros2/srv/ServoJ
**Type:** `dobot_msgs_v4/srv/ServoJ`

```
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] param_value

---
int32 res
```

### /dobot_bringup_ros2/srv/ServoP
**Type:** `dobot_msgs_v4/srv/ServoP`

```
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] param_value

---
int32 res
```

### /dobot_bringup_ros2/srv/RelJointMovJ
**Type:** `dobot_msgs_v4/srv/RelJointMovJ`

```
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] param_value

---
int32 res
```

### /dobot_bringup_ros2/srv/RelMovJUser
**Type:** `dobot_msgs_v4/srv/RelMovJUser`

```
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] param_value

---
int32 res
```

### /dobot_bringup_ros2/srv/RelMovLTool
**Type:** `dobot_msgs_v4/srv/RelMovLTool`

```
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] param_value

---
int32 res
```

### /dobot_bringup_ros2/srv/RelMovLUser
**Type:** `dobot_msgs_v4/srv/RelMovLUser`

```
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
string[] param_value

---
int32 res
```

### /dobot_bringup_ros2/srv/Arc
**Type:** `dobot_msgs_v4/srv/Arc`

```
bool mode
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
float64 a2
float64 b2
float64 c2
float64 d2
float64 e2
float64 f2

string[] param_value
---
int32 res
```

### /dobot_bringup_ros2/srv/Circle
**Type:** `dobot_msgs_v4/srv/Circle`

```
bool mode
float64 a
float64 b
float64 c
float64 d
float64 e
float64 f
float64 a2
float64 b2
float64 c2
float64 d2
float64 e2
float64 f2
int32 count
string[] param_value
---
int32 res
```

## 3. Motion Parameters

### /dobot_bringup_ros2/srv/SpeedFactor
**Type:** `dobot_msgs_v4/srv/SpeedFactor`

```
int32 ratio
---
int32 res
```

### /dobot_bringup_ros2/srv/AccJ
**Type:** `dobot_msgs_v4/srv/AccJ`

```
# r --> 1 - 100
int32 r
---
int32 res
```

### /dobot_bringup_ros2/srv/AccL
**Type:** `dobot_msgs_v4/srv/AccL`

```
# r --> 1 - 100
int32 r
---
int32 res
```

### /dobot_bringup_ros2/srv/VelJ
**Type:** `dobot_msgs_v4/srv/VelJ`

```
int32 r
---
int32 res
```

### /dobot_bringup_ros2/srv/VelL
**Type:** `dobot_msgs_v4/srv/VelL`

```
int32 r
---
int32 res
```

### /dobot_bringup_ros2/srv/CP
**Type:** `dobot_msgs_v4/srv/CP`

```
# r --> 1 - 100
int32 r
---
int32 res
```

## 4. Drag & Path

### /dobot_bringup_ros2/srv/DragSensivity
**Type:** `dobot_msgs_v4/srv/DragSensivity`

```
int32 index
int32 value
---
int32 res
```

### /dobot_bringup_ros2/srv/StartDrag
**Type:** `dobot_msgs_v4/srv/StartDrag`

```
---
int32 res
```

### /dobot_bringup_ros2/srv/StopDrag
**Type:** `dobot_msgs_v4/srv/StopDrag`

```
---
int32 res
```

### /dobot_bringup_ros2/srv/StartPath
**Type:** `dobot_msgs_v4/srv/StartPath`

```
string trace_name
string[] param_value
---
int32 res
```

### /dobot_bringup_ros2/srv/RunScript
**Type:** `dobot_msgs_v4/srv/RunScript`

```
string project_name
---
int32 res
```

## 5. IO - Write ouput

### /dobot_bringup_ros2/srv/AO
**Type:** `dobot_msgs_v4/srv/AO`

```
# index --> 1 - 2
# value --> 0 - 10
int32 index
int32 value
---
int32 res
```

### /dobot_bringup_ros2/srv/AOInstant
**Type:** `dobot_msgs_v4/srv/AOInstant`

```
# index --> 1 - 2
# value --> 0 - 10
int32 index
int32 value
---
int32 res
```

### /dobot_bringup_ros2/srv/DO
**Type:** `dobot_msgs_v4/srv/DO`

```
int32 index
int32 status
int32 time
---
int32 res
```

### /dobot_bringup_ros2/srv/DOInstant
**Type:** `dobot_msgs_v4/srv/DOInstant`

```
int32 index
int32 status
---
int32 res
```

### /dobot_bringup_ros2/srv/DoGroup
**Type:** `dobot_msgs_v4/srv/DOGroup`

```
int32[] args
---
int32 res
```

### /dobot_bringup_ros2/srv/SetOutputBool
**Type:** `dobot_msgs_v4/srv/SetOutputBool`

```
int32 address
int32 value
---
int32 res
```

### /dobot_bringup_ros2/srv/SetOutputFloat
**Type:** `dobot_msgs_v4/srv/SetOutputFloat`

```
int32 address
float64 value
---
int32 res
```

### /dobot_bringup_ros2/srv/SetOutputInt
**Type:** `dobot_msgs_v4/srv/SetOutputInt`

```
int32 address
int32 value
---
int32 res
```

### /dobot_bringup_ros2/srv/ToolDO
**Type:** `dobot_msgs_v4/srv/ToolDO`

```
int32 index
int32 status
---
int32 res
```

### /dobot_bringup_ros2/srv/ToolDOInstant
**Type:** `dobot_msgs_v4/srv/ToolDOInstant`

```
int32 index
int32 status
---
int32 res
```

## 6. Modbus/Register

### /dobot_bringup_ros2/srv/ModbusCreate
**Type:** `dobot_msgs_v4/srv/ModbusCreate`

```
string   ip
int32    port
int32    slave_id
int32    is_rtu
---
string robot_return
int32    res
```

### /dobot_bringup_ros2/srv/ModbusRTUCreate
**Type:** `dobot_msgs_v4/srv/ModbusRTUCreate`

```
int32   slave_id
int32   baud
string  parity
int32   data_bit
int32   stop_bit
---
string robot_return
int32 res
```

### /dobot_bringup_ros2/srv/ModbusClose
**Type:** `dobot_msgs_v4/srv/ModbusClose`

```
int32 index
---
int32 res
```

### /dobot_bringup_ros2/srv/SetCoils
**Type:** `dobot_msgs_v4/srv/SetCoils`

```
int32    index
int32    addr
int32    count
string   val_tab
---
int32 res
```

### /dobot_bringup_ros2/srv/SetHoldRegs
**Type:** `dobot_msgs_v4/srv/SetHoldRegs`

```
int32    index
int32    addr
int32    count
string   val_tab
string   val_type
---
int32 res
```

## 7. Safety

### /dobot_bringup_ros2/srv/BrakeControl
**Type:** `dobot_msgs_v4/srv/BrakeControl`

```
int32 axis_id
int32 value
---
int32 res
```

### /dobot_bringup_ros2/srv/SetCollisionLevel
**Type:** `dobot_msgs_v4/srv/SetCollisionLevel`

```
int32 level
---
int32 res
```

### /dobot_bringup_ros2/srv/SetPostCollisionMode
**Type:** `dobot_msgs_v4/srv/SetPostCollisionMode`

```
int32 mode
---
int32 res
```

### /dobot_bringup_ros2/srv/EnableSafeSkin
**Type:** `dobot_msgs_v4/srv/EnableSafeSkin`

```
int32 status
---
int32 res
```

### /dobot_bringup_ros2/srv/SetSafeSkin
**Type:** `dobot_msgs_v4/srv/SetSafeSkin`

```
int32 part
int32 status
---
int32 res
```

### /dobot_bringup_ros2/srv/SetSafeWallEnable
**Type:** `dobot_msgs_v4/srv/SetSafeWallEnable`

```
int32 index
int32 value
---
int32 res
```

### /dobot_bringup_ros2/srv/SetBackDistance
**Type:** `dobot_msgs_v4/srv/SetBackDistance`

```
float64 distance
---
int32 res
```

## 8. Tool/User/Payload

### /dobot_bringup_ros2/srv/SetTool
**Type:** `dobot_msgs_v4/srv/SetTool`

```
int32 index
string value
---
int32 res
```

### /dobot_bringup_ros2/srv/SetTool485
**Type:** `dobot_msgs_v4/srv/SetTool485`

```
int32  baudrate
string parity
int32  stop
int32  identify
---
int32 res
```

### /dobot_bringup_ros2/srv/SetToolMode
**Type:** `dobot_msgs_v4/srv/SetToolMode`

```
int32 mode
int32 type
---
int32 res
```

### /dobot_bringup_ros2/srv/SetToolPower
**Type:** `dobot_msgs_v4/srv/SetToolPower`

```
int32 status
---
int32 res
```

### /dobot_bringup_ros2/srv/SetUser
**Type:** `dobot_msgs_v4/srv/SetUser`

```
int32 index
string value
---
int32 res
```

### /dobot_bringup_ros2/srv/CalcTool
**Type:** `dobot_msgs_v4/srv/CalcTool`

```
int32  index
int32  matrix
string offset
---
int32 res
```

### /dobot_bringup_ros2/srv/CalcUser
**Type:** `dobot_msgs_v4/srv/CalcUser`

```
int32  index
int32  matrix
string offset
---
int32  res
```

### /dobot_bringup_ros2/srv/Tool
**Type:** `dobot_msgs_v4/srv/Tool`

```
int32 index
---
int32 res
```

### /dobot_bringup_ros2/srv/ToolAI
**Type:** `dobot_msgs_v4/srv/ToolAI`

```
int32 index
---
int32 res
```

### /dobot_bringup_ros2/srv/ToolDI
**Type:** `dobot_msgs_v4/srv/ToolDI`

```
int32 index
---
int32 res
```

### /dobot_bringup_ros2/srv/User
**Type:** `dobot_msgs_v4/srv/User`

```
int32 index
---
int32 res
```

### /dobot_bringup_ros2/srv/SetPayload
**Type:** `dobot_msgs_v4/srv/SetPayload`

```
float64 load
float64 x
float64 y
float64 z
---
int32 res
```









