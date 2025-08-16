# WaterMarkLab

[![English](README.md) | [![中文](README_zh.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)

A lightweight, single-file Flask web application for exploring and applying LSB (Least Significant Bit) steganography and DCT-based emergent visual watermarking techniques.

This tool is designed for educational purposes and experiments, providing a user-friendly interface to understand the fundamentals of digital watermarking. It is Termux-friendly for easy deployment on mobile devices.

![Screenshot of WaterMarkLab UI](https://user-images.githubusercontent.com/YOUR_USER_ID/YOUR_REPO_ID/...)
*(Suggestion: Please replace this with a real screenshot of your application's UI)*

---

### Features

* **Dual Watermarking Techniques**:
    * **LSB Steganography**: Embed invisible data (text or images) by modifying the least significant bits of image pixels.
    * **DCT Emergent Watermark**: Add a semi-visible watermark in the frequency domain that "emerges" after JPEG compression or resizing.
* **Rich Parameter Control**:
    * **Presets**: `stealth`, `balanced`, and `robust` presets for quick setup.
    * **LSB Bits (bpc)**: Use 1 or 2 bits per color channel for embedding.
    * **Redundancy**: Repeat each data bit multiple times to resist data loss.
    * **Scattering**: Randomly distribute watermark data across the image to defend against cropping.
    * **Channel Selection**: Choose which color channels (R, G, B) to use.
* **Intuitive Web Interface**:
    * A clean, single-page UI with light and dark modes.
    * Supports both text and image watermarks.
    * Real-time JPEG quality preview to simulate compression effects.
    * Built-in watermark detection and extraction.
* **Self-Contained & Portable**:
    * Written as a single Python file with minimal dependencies.
    * Temporary file cleanup mechanism.

### Getting Started

#### Prerequisites

- Python 3.9 or higher is recommended.
- `pip` for installing packages.

#### Installation

1.  Clone the repository:
    ```bash
    git clone [https://github.com/Flen-Plnens/WaterMarkLab.git](https://github.com/Flen-Plnens/WaterMarkLab.git)
    cd WaterMarkLab
    ```

2.  Install the required dependencies:
    ```bash
    pip install --user Flask Pillow opencv-python-headless numpy
    ```

3.  Run the application:
    ```bash
    python app.py
    ```
    The application will start on `http://127.0.0.1:5000`. If port 5000 is in use, it will automatically try ports 5001-5010.

### Usage

1.  **Open** your web browser and navigate to `http://127.0.0.1:5000`.
2.  **Upload a Carrier Image**: Click "Choose Image File..." to select the image you want to add a watermark to.
3.  **Configure Watermark**:
    * Select the watermark type (`text` or `image`).
    * Enter your text or upload a watermark image.
    * Choose a preset (`balanced` is a good starting point).
    * Fine-tune the parameters (LSB bits, redundancy, etc.) as needed.
4.  **Embed**: Click the "Embed" button. The processed image and detection results will appear on the right.
5.  **Detect**: To extract a watermark, upload a suspect image and click the "Detect/Extract" button.

### License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

### Acknowledgments

* The user interface is built with the custom `subtlekit.css` framework.
