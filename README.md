# 🏋️AI-Trainer
This project is a real-time arm-curl counter built with MediaPipe and OpenCV.
It allows the user to select Left or Right arm simply by showing a left or right thumbs-up gesture, and then tracks and counts curls for the selected arm.

#⚙️ How It Works
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

#📦 Dependencies

Make sure you have:

pip install mediapipe opencv-python numpy

#▶️ Running the App
You will see:

Gesture menu → show thumbs up to choose arm

Workout window → perform curls

Program counts up to 30 reps, then returns to menu

Press Q anytime to quit.


