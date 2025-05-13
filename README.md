# Gesture Detection System
> [Documentation](https://docs.google.com/document/d/1ibAFSSe_1cYrLPXme5SaOQHpOIL54ppLaHoBJNgK54A/edit?usp=sharing)

## Overview
A lightweight, real-time hand gesture detection system using MediaPipe and Dynamic Time Warping (DTW) for gesture matching. The system allows users to define custom gestures and link them to commands, enabling hands-free control for desktop applications.

## Features
- **Real-time Gesture Recognition:** Detects gestures frame-by-frame using keypoints and DTW.
- **Customizable Gestures:** Record and save your own gestures on-the-fly.
- **No Deep Learning Models:** Efficient and lightweight, no need for GPU resources.
- **Hands-free Control:** Use gestures to control applications, play/pause media, or simulate keyboard and mouse actions.

## Requirements

### Python Libraries:
- **mediapipe**: Hand gesture detection and tracking
- **numpy**: Numerical operations and array manipulation
- **opencv-contrib-python**: Video processing
- **fastdtw**: Fast Dynamic Time Warping for gesture matching
- **scipy**: Distance metrics and scientific computations
- **matplotlib**: For visual debugging
- **jsonschema**: Validates JSON format
- **pillow**: Image handling
- **customtkinter**: Customizable GUI
- **PyAutoGUI**: Simulates mouse and keyboard actions
- **fastapi**: Backend API framework
- **requests**: Makes HTTP requests for API
- **python-dotenv**: Manages environment variables

### Hardware:
- CPU (GPU optional)
- Webcam for real-time input

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/Sh1vT/gestura-algo.git
    cd gesture-detection-system
    ```

2. **Create and activate a virtual environment:**
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

## Running the System

1. **Run the base algorithm:**
    ```bash
    jupyter notebook base_algorithm.ipynb
    ```

2. **Test gesture recording and detection in real-time.**

### For Android & Web Integration
- Set up the FastAPI backend and connect to your mobile app or web frontend.

## Algorithm Overview

- **Dynamic Time Warping (DTW):** Optimized version for gesture sequence comparison, with time complexity reduced from O(N²) to O(N).
- **Matching Stages:** Gestures are recognized sequentially from start → mid1 → mid2 → end.
- **Real-time Processing:** The system works frame-by-frame, ensuring low-latency interaction.

## Complexity

- **Time Complexity:** O(G × N × M)
  - G = Number of gestures
  - N = Number of keypoints per gesture (2x11)
  - M = Number of frames per gesture (start, mid1, mid2, end)
  
- **Space Complexity:** O(G × N × 3)
  - G = Number of stored gestures
  - N = Number of keypoints per gesture
