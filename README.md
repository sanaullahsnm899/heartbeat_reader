# ❤️ AI Heartbeat Reader — Camera-Based rPPG

A Python computer-vision experiment that estimates **heart rate (BPM)** from subtle changes in facial skin color in a recorded video, using **remote photoplethysmography (rPPG)** and signal processing.

**Notebook:** `heartbeat_reader.ipynb`

## Features
- Detects faces using an OpenCV Haar cascade and selects the largest visible face.
- Extracts a **forehead region of interest (ROI)** and tracks average green-channel intensity.
- Processes the signal using detrending, a Butterworth band-pass filter, and an FFT to estimate pulse frequency.
- Uses a configurable **10-second signal window**, BPM range, and smoothing factor.
- Overlays the face/forehead region, estimated BPM, and pulse waveform on the output video.

## Technologies
Python, OpenCV, NumPy, SciPy (`scipy.signal`), Google Colab.

## Getting Started
1. Open the notebook in **Google Colab**.
2. Run its OpenCV setup cell; **restart the runtime if instructed**, then run the remaining cells in order.
3. Upload a face video with steady lighting, minimal movement, and at least **10–12 seconds** of footage.
4. Optionally tune `WINDOW_SECONDS`, `MIN_BPM`, `MAX_BPM`, and `BPM_SMOOTHING`.
5. Run the processing cell to create `heartbeat_output.mp4`. Saving to Drive is optional.

**Dependencies:**
```bash
pip install opencv-contrib-python-headless numpy scipy
```

## Output
`heartbeat_output.mp4` — an annotated video with BPM estimation and a waveform panel.

## Limitations
**Not a medical device and not suitable for diagnosis or monitoring emergencies.** Estimates can be distorted by face motion, compression, changes in lighting, skin-region selection, and low frame rate. The algorithm estimates a dominant pulse-like frequency and does not guarantee an accurate heart-rate measurement.

**Maintainer:** [@sanaullahsnm899](https://github.com/sanaullahsnm899)
