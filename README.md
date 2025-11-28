# 🏋️AI-Trainer
This project is a real-time arm-curl counter built with MediaPipe and OpenCV.
It allows the user to select Left or Right arm simply by showing a left or right thumbs-up gesture, and then tracks and counts curls for the selected arm.

# ⚙️ How It Works
1. Gesture Menu — Select Left or Right Arm

The program begins by detecting a thumbs-up gesture using a MediaPipe hands model.

If the user shows:

👍 left hand → selects LEFT ARM

👍 right hand → selects RIGHT ARM

Once selected, the workout mode starts automatically.

2. Pose Tracking & Angle Calculation

Using mp_pose.Pose(), the app tracks:

Shoulder

Elbow

Wrist

The angle between these points is calculated using a simple vector-based formula.

3. Rep Counting Logic

The movement is determined by angle thresholds:

Angle > 160° → Arm extended → "down" phase

Angle < 40° and previous phase was "down" → "up" phase → rep counted

Each time the user completes a full curl cycle, the counter increases by 1.

4. Set Tracking

The number of completed reps determines the current set:

Reps	Set
1–10	Set 1
11–20	Set 2
21–30	Set 3

When 30 reps are completed, the program ends the session and returns to the gesture menu.

# 📦 Dependencies

Make sure you have:

pip install mediapipe opencv-python numpy

# ▶️ Running the App
You will see:

Gesture menu → show thumbs up to choose arm

Workout window → perform curls

Program counts up to 30 reps, then returns to menu

Press Q anytime to quit.


![image alt](https://github.com/mina91gh/AI-Trainer/blob/main/AI-Trainer-GIF.gif)


# How to tweak this project for your own uses:

You can easily adapt the logic to fit different exercises or gestures.
Most of the core behavior lives inside the angle-calculation and gesture-detection parts of the code. Here are a few common tweaks:

• Detecting different gestures:
  Replace the thumbs-up detection logic with any other MediaPipe hand gesture you prefer.

• Tracking another joint or movement:
  Modify the angle-calculation points (for example, shoulder–elbow–wrist) to match the motion you want to track.

• Adjusting sensitivity:
  If the counter moves too quickly or too slowly, tune the thresholds for angle ranges and state changes.

• Changing UI or prompts:
You can update the on-screen text, colors, or feedback messages directly in the drawing functions.

# Found a Bug?

If you find a bug, have an idea, or want to improve the project:

• Open an Issue describing the problem or suggestion

• Or submit a Pull Request with your improvements



