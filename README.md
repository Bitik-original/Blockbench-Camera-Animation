# 🎬 Blockbench 3D Camera Cutscene Extension for GDevelop 5

A custom extension for **GDevelop 5** that synchronizes the scene's 3D camera with an animated camera from a **Blockbench** model (GLB / glTF), enabling cinematic cutscenes, fly-throughs, and scripted camera sequences.

---

## 1. Prerequisites

* **GDevelop 5** 
* **Blockbench** 
* Blockbench Plugin: **`Cameras`** (by *JannisX11*).
  * *Installation:* In Blockbench, go to **File ➔ Plugins...** ➔ search for **Cameras** ➔ click **Install**.

<img width="259" height="576" alt="image" src="https://github.com/user-attachments/assets/d1974a8d-e36f-438a-9d0b-294380f7727a" />
<img width="1202" height="888" alt="image" src="https://github.com/user-attachments/assets/bf82868d-7760-4618-b8df-683c39d5de4d" />

---

## 2. Step-by-Step Blockbench Setup

### Step 1: Outliner Setup
1. Switch to the **Edit** tab.
2. Click the **Add Group** button (folder icon) in the Outliner panel.
3. Rename the newly created group to: **`camera`**.
4. Go to **Edit ➔ Add Camera** (or use the Cameras plugin button).
5. Name the camera **`camera`** and **drag it inside the `camera` group**.

### Step 2: Create the Animation
1. Switch to the **Animate** tab.
2. Create a new animation (e.g., named: `cutscene_1`).
3. Set an adequate timeline duration (e.g., **`3.0`** or **`5.0`** seconds).
4. Select the **`camera` group** in the Outliner.
5. On the timeline, insert keyframes for:
   * **Position**
   * **Rotation**
6. Press Play to preview the camera path.

### Step 3: Export to GLB
1. Go to **File ➔ Export ➔ Export glTF / GLB**.
2. Make sure **Export Animations** is checked in the dialog.
3. Save the file (e.g. `cutscene.glb`).

<img width="154" height="53" alt="image" src="https://github.com/user-attachments/assets/4e4526f0-cae1-42a0-ad07-14ddd31462cb" />

---

## 3. Step-by-Step GDevelop 5 Setup

### Step 1: Import the Extension
1. In GDevelop, open the left panel and click on **Extensions**.
2. Click **Import an extension** at the bottom.
3. Choose the [[`BlockbenchCamera.json`](BlockbenchCamera.json](https://github.com/Bitik-original/Blockbench-Camera-Animation/releases)) file.

### Step 2: Add the 3D Model
1. In the Object panel, click **Add a new object ➔ 3D Model**.
2. Choose your `cutscene.glb` file.
3. In the Animations list, add your exported animation (e.g. `cutscene_1`).
4. **Drag the 3D model instance onto the scene canvas!**

---

## 4. Parameters & Features

In the **«Capture camera from animation of model»** action:

| Parameter | Default | Description |
| :--- | :---: | :--- |
| **3D Model** | — | The 3D model instance on the scene. |
| **Camera node name** | `"camera"` | The group/node name in the GLB file. |
| **Layer** | `""` | Target layer name (empty for base layer). |
| **Camera index** | `0` | Camera number on the layer (default: 0). |
| **Stop on end?** | `yes` | Automatically release the camera when animation ends. |
| **Sync FOV?** | `yes` | Synchronize camera field of view from Blockbench. |
| **Smooth transition?** | `no` | **Toggle (Yes / No)** for cinematic flight (Lerp & Slerp). |
| **Fly-in duration (s)** | `1.0` | Seconds to smoothly fly from player view into cutscene. |
| **Return duration (s)** | `1.0` | Seconds to smoothly return to player view at the end. |
| **Smoothness (0..0.95)** | `0` | Steadicam inertia smoothing. `0` = rigid 1:1 lock. |
