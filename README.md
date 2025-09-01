# Audio Amplifier Quality Control

## Overview
This repository contains the source code and documentation for the **Audio Amplifier Quality Control** project developed by **GOATS Corp.** (Generation, Obtention, Assessment and Treatment of Signal Corporation). This MATLAB-based software suite is designed to evaluate and optimize audio amplifier performance. It was developed as part of an academic effort at **Universitat Politècnica de Catalunya (UPC) BarcelonaTech**.

The suite consists of three main components:
1. **Signal Measurement System**: Generates or records audio signals, analyzes metrics like power, gain, and Total Harmonic Distortion (THD), and visualizes waveforms, spectrograms, and frequency responses.
2. **Class D Amplifier Simulator**: Simulates a Class D amplifier using Pulse Width Modulation (PWM) techniques, including resampling, triangular wave generation, comparison, and low-pass filtering.
3. **Interactive Audio Equalizer**: Allows users to apply parametric filters (Bell, Shelf, Band, HighCut, LowCut), visualize frequency responses, and play/export filtered audio.

The suite supports mono and stereo audio, synthetic signal generation (sine, square, triangle, chirp, saturated), and seamless integration between components for comprehensive audio analysis.

## Features
- **Signal Generation & Recording**:
  - Create synthetic signals or record via microphone.
  - Configurable duration (0.1–30s) and frequency (1Hz–10kHz).
- **Analysis Metrics**:
  - Compute power (mean square value), gain (dB), and THD (%).
  - Color-coded waveforms based on THD: green (<10%), orange (10–20%), red (≥20%).
- **Visualization**:
  - Time-domain waveforms, spectrograms, and FFT-based frequency responses.
- **Amplification Modes**:
  - None, Simulated (via Class D simulator), or External (user-connected amplifier).
- **Equalization**:
  - Customizable filters with real-time previews.
  - Audio segmentation using Hamming windows.
  - Playback controls.
- **File I/O**:
  - Import/export `.wav` files.
  - Save/load configurations as `.mat` files.
- **Simulation**:
  - Adjustable parameters for triangle wave frequency, comparator amplitude, and low-pass cutoff in the amplifier simulator.

## Requirements
### Hardware
- Audio output device (speakers/headphones) for playback.
- Microphone for recording mode.
- Sufficient system memory for large audio files.

### Software
- **MATLAB R2021a** or newer (tested on R2024b).
- **MATLAB App Designer** (included in base MATLAB).
- **Audio Toolbox** (for `audioplayer`, `audioread`, etc.).
- No additional toolboxes required.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/audio-amplifier-quality-control.git
   ```
2. Open MATLAB and navigate to the project directory.
3. Ensure the required toolboxes are installed (run `ver` in MATLAB to check).
4. Add the project folder to your MATLAB path if needed:
   ```matlab
   addpath(genpath('path/to/project'));
   ```

## Usage
### Running the Applications
1. **Signal Measurement System**:
   - Open and run `MScomentat.mlapp` in MATLAB App Designer.
   - Select mode (synthetic/recorded), signal type, duration, and frequency.
   - Use "Run" to generate/record, "Refresh" to update plots/metrics.
   - Play, import/export signals, and choose amplification mode.
2. **Class D Amplifier Simulator**:
   - Open and run `DClassAmplifier.mlapp`.
   - Generate sine waves or load audio files.
   - Adjust parameters (e.g., working frequency, triangle frequency).
   - Run simulation and export outputs.
3. **Equalizer**:
   - Open and run `EQapp.mlapp`.
   - Load audio files (`.wav`/`.mp3`).
   - Add/edit filters via the toolbar.
   - Visualize responses, play/pause, and export filtered audio.

### Example Workflow
1. Generate a sine wave in the Signal Measurement System.
2. Simulate amplification using the Class D Simulator (integrated in "simulated" mode).
3. Equalize the output in the Equalizer app.
4. Analyze THD/gain and visualize results.

For detailed usage, refer to the **User's Manual** and **Programmer's Manual**.

## Documentation
- **User's Manual**: `GOATS User's Manual.pdf` - Step-by-step guide to using the apps.
- **Programmer's Manual**: `PROGRAMMERS MANUAL GOATS.docx` - Code structure, functions, and troubleshooting.
- **Final Report**: `FINALREPORT.docx` - Project overview, design, implementation, characterization, budget, conclusions, and reflections.
- **Requirements & Specifications**: `REQUIREMENTSSPECIFICATIONS.pdf` - Detailed requirements and specs.
- **Project Plan**: `ProjectPlan.pdf` - Time plan, team roles, and distribution.

## Troubleshooting
- **Audio not loading/playing**: Ensure supported formats (`.wav`/`.mp3`) and check audio device settings in MATLAB.
- **GUI not responding**: Update MATLAB/graphics drivers; use R2021a+.
- **Simulation failures**: Verify parameter values (e.g., signal lengths match); reduce frequencies for large signals.
- **Integration issues**: Ensure apps are in the same directory; restart MATLAB if needed.

For more details, see the troubleshooting section in the **Programmer's Manual**.
