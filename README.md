# Biomechanical-coverdrive-analysis-ComputerVision

This repository contains a real-time computer vision system for evaluating cricket cover drives using 2D pose estimation and biomechanical analysis. The system extracts key joint angles frame-by-frame, overlays metrics and coaching feedback on the video, and produces a structured performance evaluation report.

---

## Repository Structure

```
.
├── Final_Athlete_Assignment.ipynb          # Main Colab notebook (recommended interface)
├── final_athlete_assignment_aspython.py    # Equivalent .py script version
├── annotated_final_fixed.mp4               # Output video with live pose + feedback overlays
├── evaluation.json                         # Final multi-category score and feedback file
├── Stunning cover drive ....mp4            # Input video (YouTube Short, pre-downloaded)
├── README.md                               # Project documentation
├── LICENSE                                 # MIT License
```

---

## How to Run the Project (Colab Instructions)

This project is intended to be run in [Google Colab](https://colab.research.google.com/). Follow the steps below to reproduce the analysis:

### 1. Upload the Notebook
- Download `Final_Athlete_Assignment.ipynb` from this repository.
- Open it in Google Colab by uploading the file.

### 2. Install Required Packages
Run the first code cell in the notebook:

```python
!pip install mediapipe opencv-python pytube
```

You will be prompted to **restart the runtime** after this cell. Accept the restart before proceeding.

### 3. Upload the Input Video
- Download the input video file from this repository:
  `Stunning cover drive #cricket #batreview #cricketbattingpractice #ytshorts.mp4`
- Upload it manually into the Colab environment using the file sidebar.
- Rename it for consistency:

```python
import os
os.rename("/content/Stunning cover drive #cricket #batreview #cricketbattingpractice #ytshorts.mp4",
          "/content/cover_drive.mp4")
```

### 4. Run the Notebook Cell-by-Cell
The notebook is modular and structured as follows:
- Pose estimation setup
- Joint angle extraction and calculation
- Real-time overlay of metrics and feedback
- Persistent cumulative issue panel
- Generation of final `evaluation.json` report

---

## Output Artifacts

- `annotated_final_fixed.mp4`: Full-length video with overlaid pose skeleton, angle metrics, frame-level coaching feedback, and persistent evaluation summaries.
- `evaluation.json`: Structured output containing scores (1–10) for:
  - Footwork
  - Head Position
  - Balance
  - (Swing Control and Follow-through are marked as "Not evaluated")

---

## System Requirements

This project is intended for execution in Google Colab. If you wish to run it locally, the following dependencies must be installed:

```
mediapipe
opencv-python
pytube
```

Python version: 3.7+

---

## Assumptions and Limitations

- Pose estimation is based on MediaPipe's 2D landmark detection; no 3D joint inference is performed.
- The system assumes a single batter is present in the video with a mostly front-facing or side-on camera angle.
- Swing Control and Follow-through metrics are not computed in the base version due to the absence of bat tracking.
- Input videos must clearly show the batter’s body with minimal occlusion for accurate pose extraction.

---

## License

This project is released under the MIT License. See `LICENSE` for details.

---

## Author

Developed by Aditya Vikram Singh  
As part of the AthleteRise Internship Assignment (AI-Powered Sports Analytics)

