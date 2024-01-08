# Unity Scripts

**IMPORTANT:** Do *not* rename script files. Unity uses the file name to create and access a MonoBehaviour class.

---------------

## CameraFollow.cs
Instructs a camera GameObject to follow a targeted GameObject. This could be a player character, vehicle, or non-player character (NPC).

### Usage
- Add script to any camera GameObject (usually the Main Camera) in a scene.
- Select a GameObject you want to follow as the Target parameter.
- Set the Offset position (usually a negative integer in the Z-axis).

---------------

## Collect.cs
Causes a collectible item to be destroyed or disappear when the player GameObject collides with it.

### Usage
- Add script to any collectible GameObject, like a gem or coin.
- Optional: Add an Audio Clip to Collision Audio parameter if you want audio to play when *any* collision occurs.

---------------

## PlayerControls.cs & Player2Controls.cs
Controls a character with 360-degree rotation, forward running, and jump movement. These scripts are good for controlling a character in an open game environment. When both scripts are used, two player GameObjects can be controlled in the same game environment by two players.

### Usage
- Add script to a player 1 or player 2 character GameObject. (Use PlayerControls.cs for Player 1 and Player2Controls.cs for Player 2 GameObject.)
- Required: For Controller, select the GameObject's Character Controller component.
- Required: For Anim, select the GameObject's Animator file.
- Optional: Add an Audio Clip to Running Sound parameter if you want audio to play whenever the character is running.
- Adjust the player GameObject's running speed as needed. Speed default is 4.
- Adjust the player GameObject's rotational speed as needed. Rot Speed default is 90.
- Adjust Rot as needed. Default is 0.
- Adjust Gravity as needed. Default is 8. Less gravity impact will impact jump movement.
- Leave Running unchecked. This will change as you control your character in Play mode.

### Player Controls
- ARROW UP = Forward
- ARROW RIGHT = Rotate Right
- ARROW LEFT = Rotate Left
- SPACE = Jump

### Player 2 Controls
- W = Forward
- D = Rotate Right
- A = Rotate Left
- S = Jump

**NOTE:** The keyboard controls for these scripts are hardcoded and cannot be altered in Unity's Project Settings.

---------------

## RotateHover.cs
A simple script that rotates and hovers a GameObject. This script can be used to add movement to collectible GameObjects. The hover movement uses Unity's PingPong method.

### Usage
- Add script to a GameObject, such as a collectible item.
- Check mark Rotate if you want the object to rotate along the Y-axis.
- Adjust Rotation Speed parameter with an integer value as needed. There is no default speed.
- Adjust Hover Speed parameter with an integer value as needed. There is no default speed.
- Adjust Hover Distance with integer values as needed. There is no default distance.

---------------

## VehicleControl.cs
Controls a vehicle's wheels with rotation of wheel meshes using wheel colliders. This script also allows the player to steer the vehicle.

### Usage
- Add script to the parent vehicle GameObject.
- Be sure to set up pairs of wheel meshes (right and left for each axle of your vehicle) in one child GameObject of the parent vehicle GameObject.
- Be sure to set up pairs of wheel colliders (right and left for each axle of your vehicle) in one child GameObject of the parent vehicle GameObject.
- In the script's properties, add the number of axles your vehicle needs controlled.
- For each axle, add a wheel mesh and wheel collder for each wheel on that axle.
- Select at least 1 axle to provide power by checking Motor. (More axles connected to Motor will give your vehicle more power.)
- If you want steering, check Steering on at least one axle.

The remaining script properties control the vehicles torque (motor and brake), deceleration force (how quickly the vehicle comes to a stop), and steering angle (how far the wheels can turn when steering the vehicle).

These remaining parameters default to 0. However, here are some suggested values.

- Max Motor Torque = -800 (-/+ changes the direction of the motor)
- Max Steering Angle = 30
- Brake Torque = 400
- Deceleration Force = 200

**NOTE:** If your vehicle tilts too much or flips over easily while turning, try adjusting the vehicle's Mass under the parent GameObject's Rigidbody component. The more mass, the less easily it will be for your vehicle to tip over. You can also adjust your vehicle's Drag in the Rigidbody component to create more or less air resistance against your vehicle.