# 👁️🖱️ Eye-Controlled Mouse using Python, MediaPipe, and OpenCV

This project allows users to control their computer mouse cursor and perform click actions **using only their eyes**. It leverages computer vision and facial landmark detection to track eye movement and blinks as input events.

## 📌 Features

- 🎯 Cursor movement based on eye position
- 🖱️ Blink-based mouse clicks
- 🔍 Real-time facial landmark detection
- 🧠 No need for physical input devices like a mouse or trackpad

## 🛠️ Technologies Used

- **Python 3**
- [OpenCV](https://opencv.org/) - for webcam access and image processing
- [MediaPipe](https://developers.google.com/mediapipe) - for face and eye landmark detection
- [PyAutoGUI](https://pyautogui.readthedocs.io/) - for mouse movement and click simulation

## 📽️ How It Works

1. The webcam captures the live video feed.
2. MediaPipe detects facial landmarks.
3. The coordinates of specific eye landmarks are used to:
   - Move the cursor (`landmarks[474:478]`)
   - Detect blink by measuring the distance between two upper eyelid landmarks (`landmarks[145]` and `landmarks[159]`)
4. A blink (if the distance between landmarks is small enough) triggers a mouse click.

## ▶️ How to Run
### 1. Install dependencies

```bash
pip install opencv-python mediapipe pyautogui


2. Run the script
bash
Copy
Edit
python eye_mouse.py
Make sure your webcam is connected and enabled.

⚙️ Configuration
Eye movement threshold for click detection is currently set to 0.013. You can adjust this for sensitivity in:

python
Copy
Edit
if (left[0].y - left[1].y) < 0.013:
Screen resolution is automatically detected with:

python
Copy
Edit
screen_w, screen_h = pyautogui.size()
🖼️ Screenshot

(You can add your own screenshot named screenshot.png in the repo root.)

📌 Limitations & Future Work
1. Works best in well-lit environments
2. May struggle with glasses or dark lighting
3. Can be extended to:
4. Support both eyes for better accuracy
5. Add calibration and gesture control
6. Introduce on-screen dwell buttons for click alternatives

📜 License
This project is open source and available for educational and research purposes.
