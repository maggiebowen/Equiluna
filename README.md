# Equiluna: Multisensory Balance Board Video Game

Supplementary Code for CHItaly 2025 Submission

## Overview

This repository contains the full source code for Equiluna, a balance training system that combines a custom-built mediolateral balance board with a 2D video game interface. The system evaluates user performance under different sensory feedback conditions (auditory, haptic, audio-haptic) using real-time IMU data. This codebase is provided to support the reproducibility and extension of our CHItaly 2025 study.

## Repo Structure
```text
Equiluna/
├── auditory_files/         # Pure Data patches for auditory feedback
├── results/                # Participant data from experimental trials
├── sensors_and_actuators/  # Arduino code for IMU input and haptic motor control
├── visual/                 # Processing sketch for the 2D balance game
│   ├── data/               # Fonts used in the game UI
│   └── image/              # Visual assets and icons for gameplay
├── README.md               # This documentation file
```

## System Requirements
• Microcontroller: Teensy 3.6

• Sensor: Adafruit BNO055 IMU
• Actuators: 4x ERM vibration motors
• Speaker: External speaker (e.g., JBL GO or similar)
• Display: Projector or external monitor
• Computer: Tested on macOS and Linux (Ubuntu 22.04)

## Software Dependencies
• Processing 3.5.4 (or later)
• Required libraries: serial, controlP5 (install via Processing IDE)
• Arduino IDE (1.8+)
• Teensyduino plugin required for Teensy 3.6
• Adafruit BNO055 library
• Pure Data (Pd) (0.52+)
• Required for real-time sound synthesis

## Setup Instructions
1. IMU + Balance Board
• Mount the BNO055 IMU ~16 cm from center under the skateboard deck.
• Connect the IMU to the Teensy 3.6 microcontroller.
2. Upload Arduino Sketch
• Open the sketch in /Arduino/ and upload to the Teensy using Arduino IDE.
• Ensure correct COM port and board settings.
3. Launch Pure Data Patch
• Open PureData/audio-feedback.pd.
• Enable DSP (toggle “Audio ON”) and ensure proper audio output.
4. Run Game in Processing
• Open /Processing/EquilunaGame.pde.
• Start the game. The astronaut avatar should respond to board tilt.
• Feedback will activate based on deviation from the path. Remember to set the feedback type to TRUE before running.

## Gameplay Instructions
• Players stand barefoot on the balance board.
• Lean left/right to guide the astronaut avatar along a predefined path.
• Feedback conditions (None, Haptic, Auditory, Audio-Haptic) can be changed in the code.
• Performance is measured using two metrics: Accuracy (on-path adherence) and Similarity (trajectory smoothness).

## Citation

If you use or reference this system in your work, please cite:

Benedicto, M., Bowen, M., & Reyes, A. (2025). Enhancing balance through multisensory gaming: Evaluating haptic and auditory cues for rehabilitation. In Proceedings of the 16th Biannual Conference of the Italian SIGCHI Chapter (CHItaly ’25).

## License

This work, including the source code and documentation, is licensed under a  
**Creative Commons Attribution–NonCommercial–NoDerivatives 4.0 International License (CC BY-NC-ND 4.0)**.

You may share this work with attribution for non-commercial purposes, but you may not alter, transform, or build upon it.

Full license text: https://creativecommons.org/licenses/by-nc-nd/4.0/
