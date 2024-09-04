# Video Processing Tools

This repository contains two main tools for processing videos:

1. **Video to Contour Video Converter**: Converts a video to a contour video where contours of bright objects (such as LEDs) are detected and highlighted.
2. **LED Detection from Video Frames**: Analyzes video frames to detect the number of glowing LEDs, saves the grayscale, binary, and contour images, and outputs the results in JSON format.

## Features

### Video to Contour Video Converter
- Converts an input video into a contour video.
- Detects and highlights bright objects using contour detection.
- Adjustable threshold to fine-tune the contour detection process.
- Outputs the processed video with contours drawn on each frame.

### LED Detection from Video Frames
- Extracts frames from a video based on a specified sampling rate.
- Converts each frame to grayscale, applies a binary threshold, and detects contours representing glowing LEDs.
- Saves the grayscale, binary, and contour images for each frame.
- Outputs the results in JSON format, detailing the number of LEDs detected in each sampled frame.
- Includes a debugging mode that displays the grayscale, binary, and contour images.

## Requirements

- Python 3.x
- OpenCV (`cv2`)
- NumPy (`numpy`)

## Installation

1. Clone this repository to your local machine:

    ```bash
    git clone https://github.com/yourusername/video-processing-tools.git
    cd video-processing-tools
    ```

2. Install the required Python packages:

    ```bash
    pip install opencv-python numpy
    ```

## Usage

### Video to Contour Video Converter

1. Place your input video file in the `video` directory or specify the path to your video.

2. Run the `convert_video_to_contour_video.py` script:

    ```bash
    python convert_video_to_contour_video.py
    ```

3. Adjust the `input_video_path`, `output_video_path`, and `threshold` values in the script according to your needs.

    ```python
    input_video_path = 'video/sample_2.avi'  # Path to your input video
    output_video_path = 'video/sample_2_contour.avi'  # Path to save the output video
    threshold = 240  # Threshold value to detect bright objects
    ```

4. After running the script, your output video will be saved in the specified location.

### LED Detection from Video Frames

1. Place your input video file in the `video` directory or specify the path to your video.

2. Run the `process_video` function in the script:

    ```bash
    python led_detection_from_video.py
    ```

3. Adjust the `video_path`, `samples_per_minute`, `threshold`, and `debug` values in the script according to your needs:

    ```python
    video_path = 'video/sample_2.avi'  # Path to your input video
    samples_per_minute = 24  # Number of frames to sample per minute
    threshold = 100  # Threshold value for detecting glowing LEDs (default 200)
    debug = True  # Set to True to save and display images
    ```

4. After running the script, grayscale, binary, and contour images will be saved in the `outputs` directory, and a JSON file containing the LED count per frame will be generated.

## Example

### Video to Contour Video Converter Example

```python
input_video_path = 'video/sample_2.avi'
output_video_path = 'video/sample_2_contour.avi'
threshold = 240
```
convert_video_to_contour_video(input_video_path, output_video_path, threshold)


### LED Detection from Video Frames Example

```python
video_path = 'video/sample_2.avi'
samples_per_minute = 24  # Change this value as needed
threshold = 100  # Adjust the threshold based on the brightness of LEDs (default 200)
process_video(video_path, samples_per_minute, threshold, debug=True)
```
## Output
Video to Contour Video Converter
The output video will have contours drawn around the detected bright objects in each frame.

## LED Detection from Video Frames
The output directory (outputs) will contain:

Grayscale images for each sampled frame.
Binary threshold images for each sampled frame.
Contour images for each sampled frame with contours drawn around detected LEDs.
A JSON file (leds_glowing_results.json) summarizing the number of LEDs detected in each frame.

## Contributing
Contributions are welcome! Please open an issue or submit a pull request with your improvements.
