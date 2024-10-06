# Machinery 
Robotic Arm and Conveyor Belt Animation in Blender

## 1. Introduction
This in-depth guide takes you through creating a detailed and lifelike animated scene in Blender, where a robotic manipulator arm interacts with a moving conveyor belt. We’ve modeled, rigged, textured, animated, and rendered the scene, with each step accompanied by precise key commands for clarity and easy following.

## 2. Setting Up the Workspace
### Step 1: Open Blender
- Launch Blender on the computer.

### Step 2: Resetting the Scene
- Delete the already present objects in the scene so that the scene is empty.

### Step 3: Saving the Project
- Press `Ctrl + S` to save the project.
- Choose the desired directory and name the file “RoboticArm".
- Click "Save Blender File".

## 3. Modeling the Robotic Manipulator Arm
We will build the robotic arm piece by piece, starting from the base up to the gripper.
1. Press `Shift + A > Mesh > Circle`.
2. Go to Edit Mode, select the circle, and press `F` to fill in.
3. Extrude the face by pressing `E`.
4. Press `Shift + A > Mesh > Plane`.
5. Select two opposite edges, extrude by `E`, then press `Z` for moment restriction only in the Z direction.
6. Now press `Ctrl + Shift + B` for bevel edges.
7. Press `A` to select the object, then `Alt + E` > Extrude to Normal.
8. Press `Shift + A > Mesh > Cube`.
9. Scale it using `S`, then extrude it from the upper face.
10. Add a Plane, and extrude the edges downwards.
11. Then loop cut, and extrude again.
12. Add a Plane, and scale it to make it look like a plateau.
13. Then add a cube, bevel it, and through Modifier, add a Mirror to create the pick part of it.

<img src="Images/Robotic Arm Wireframe Model.png" alt="Arm" width="200"/>

## 4. Parenting in Blender for a Complete Robotic Arm
To effectively manage the movement and animation of a complete robotic arm, you can use parenting to ensure that each part of the arm moves correctly in relation to the others. Here’s how to do it:

### Step 1: Parent the Joints Sequentially
1. **Select the End Effector (e.g., Gripper):** Click on the gripper or the last part of the robotic arm.
2. **Shift-Select the Next Joint (e.g., Wrist):** Hold Shift and click on the wrist joint.
3. **Parent the Gripper to the Wrist:** Press `Ctrl + P` and select "Object." The gripper is now parented to the wrist, so it will follow the wrist's movements.

### Step 2: Continue Up the Arm
1. **Select the Wrist Joint:** Now, select the wrist joint that you just parented the gripper to.
2. **Shift-Select the Elbow Joint:** Hold Shift and click on the elbow joint.
3. **Parent the Wrist to the Elbow:** Press `Ctrl + P` and choose "Object." The wrist (and the gripper) will now follow the elbow joint's movements.

## 5. Creating Hydraulic Pistons with Constraints in Blender
To create hydraulic pistons using constraints in Blender, we have followed these steps:
1. **Model the Hydraulic Piston:**
   - Step 1: Add two cylinders (`Shift + A > Mesh > Cylinder`) for the piston body and rod. Scale them appropriately (`S` key) to fit together, with the rod slightly smaller in diameter.
2. **Parent the Rod to the Body:**
   - Step 2: Select the rod, then shift-click the body to select both. Press `Ctrl + P` and choose "Object" to parent the rod to the piston body.
3. **Apply a Track To Constraint:**
   - Step 3: Select the rod, then go to the Constraints tab (`Shift + Ctrl + C` or click the wrench icon in the Properties panel) and add a "Track To" constraint. Set the piston body as the target so the rod always points towards the body.

## 6. Creating Animation
To create the animation showing the movement of the arm, we have turned on the auto-keying and created breakpoints/markers by moving the robotic arm manually, so that when we run the animation, there is a smooth transition from each marker to the next.

## 7. Creating the Conveyor Belt
### 7.1 Basic Structure:
1. **Belt Base:** Start with a plane for the base of the conveyor belt. Adjust its dimensions to match the desired length and width of the belt.
2. **Belt Segments:** Add small rectangular segments (cubes) on top of the plane to represent the moving segments of the belt.

### 7.2 Movement Mechanism:
1. **Path Animation:** Create a path (Bezier curve) for the belt segments to follow. This path will define the direction of movement of the belt.
2. **Animating the Belt:** Parent the belt segments to the path and animate them to move along it. You can use a looped animation to simulate continuous belt movement.

### 7.3 Adding Objects on the Belt:
1. **Object Placement:** Place simple objects (e.g., cubes, spheres) on top.
2. **Animation:** Run the animation to see if the objects are falling and moving as per the conveyor belt movement.

## 8. Integration of Robotic Arm and Belt
We have then integrated the robotic arm and the belt.
