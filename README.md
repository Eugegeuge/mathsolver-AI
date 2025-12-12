# Math Solver 🧮📷

> **Real-time Handwritten Equation Solver using Computer Vision & Hybrid AI.**

**Math Solver** is an academic computer vision project developed to solve handwritten mathematical equations and operations in real-time. Inspired by industry-standard tools like Photomath, this project bridges the gap between analog writing and digital solving using a custom hybrid AI architecture.

## 🚀 Features

*   **Equation & Operation Solving**: Distinguishes between standard arithmetic (e.g., `3+5`) and linear equations (e.g., `2x+4=0`).
*   **Hybrid Recognition System**:
    *   **CNN (Convolutional Neural Network)**: Trained on MNIST for high-accuracy digit recognition (0-9).
    *   **SVM (Support Vector Machine)**: Optimized for mathematical symbols (+, -, *, /, x).
*   **Intelligent Segmentation**: Uses **HSV Color Space** to route characters to the correct model (Black Ink ➡️ Digits, Red Ink ➡️ Symbols).

## 📂 Project Structure

### `src/` (Core Logic)
Main application code and logic handlers.
*   `main_solver.py`: **Main Application**. Runs the camera loop, captures the frame, and orchestrates the recognition pipeline.
*   `equation_solver.py`: Handles the logical assembly of the equation string and solves it using **SymPy**.
*   `symbols.py`: Contains the logic for the **SVM** model to recognize mathematical operators (`+`, `-`, `*`, `/`).
*   `digit_centering.py`: **Preprocessing Utility**. Algorithm to center digits within a 28x28 bounding box, matching MNIST training conditions.
*   `dataset_inverter.py`: **Dataset Tool**. Helper script to batch-invert colors (White -> Black) for dataset augmentation.

### `training/` (Model Training)
Scripts used to create the AI models.
*   `train_model.py`: Trains the **CNN** on the MNIST dataset for digit recognition.
*   `train_custom_dataset.py`: Trains the **SVM** on our custom dataset of mathematical symbols.
*   `evaluate_model.py`: Generates confusion matrices and accuracy metrics for the trained models.

### `tests/` (Demos & Checks)
Simple scripts to test components in isolation.
*   `test_svm_single.py`: CLI script to test the **SVM** on a single image file.
*   `gui_demo.py`: **GUI Demo** (Tkinter) to load an image and predict its symbol interactively.
*   `test_cnn_single.py`: CLI script to test the **CNN** digit recognizer on a single image.

### `docs/`
*   `Memoria.pdf`: Full project documentation and academic report.

## 🛠️ Installation & Usage

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/eugegeuge/mathsolver.git
    cd mathsolver
    ```

2.  **Set up Virtual Environment (Optional but Recommended)**:
    ```bash
    python -m venv venv
    # Windows
    .\venv\Scripts\activate
    # Linux/Mac
    source venv/bin/activate
    ```

3.  **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Application**:
    ```bash
    python src/digitRecognition.py
    ```

## 👥 Authors

*   **Hugo Sevilla**
*   **Juan Diego Serrato**
*   **Hugo López**
*   **Gabriel Segovia**

---
*Built for the Computer Vision course at the University of Alicante.*
