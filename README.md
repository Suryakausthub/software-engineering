Morse Code Dataset for Tap Detection
This project generates synthetic datasets for Morse code symbol classification to train and evaluate machine learning models, including:

TinyML Model: For real-time analysis on an edge device.
Cloud-based ML Model: For processing stored data and comparative analysis.
📚 Dataset Overview
The dataset simulates Morse code inputs and evaluates classification difficulty using various noise levels and distortions. It includes two styles:

BW (Black and White): 0 for spaces, 1 for dots/dashes with bit-flip noise.
GRAY (Grayscale): Gaussian noise with varying intensities for dots/dashes.
⚙️ Dataset Generation
The dataset is generated using generate_morse_dataset.py with customizable parameters:

Frame Length: Length of each character frame.
Classes: Number of Morse symbols.
Noise Levels: Adjustable noise for realistic simulations.
Dilation Factor: To scale the lengths of symbols and spaces.
📊 Difficulty Metrics
To analyze dataset complexity, run:

bash
Copy
Edit
L, U, D, T = dataset_metrics('./baseline.npz')
Where:

L: Linear Separability
U: Uniformity
D: Density
T: Topology
📥 Loading Dataset
To load the generated dataset:

python
Copy
Edit
xtrain, ytrain, xval, yval, xtest, ytest = load_data(filename='./baseline.npz')
📦 Pre-generated Datasets
baseline.npz: Default parameters.
difficult.npz: Higher noise and random spaces.
