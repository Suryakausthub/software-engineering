📡 Morse Code Dataset for Tap Detection
This project generates synthetic datasets for Morse code symbol classification to train and evaluate machine learning models, including:

🟢 TinyML Model: For real-time analysis on an edge device.
🔵 Cloud-based ML Model: For processing stored data and comparative analysis.

📚 Dataset Overview
The dataset simulates Morse code inputs and evaluates classification difficulty by introducing different noise levels and distortions. It includes two styles:

BW (Black and White):

0 for spaces, 1 for dots/dashes.
Bit-flip noise can be added for complexity.
GRAY (Grayscale):

Gaussian noise with varying intensities for dots and dashes.
Allows modeling of more realistic signal variations.
⚙️ Dataset Generation
The dataset is generated using generate_morse_dataset.py with customizable parameters:

Frame Length: Length of each character frame.
Classes: Number of Morse symbols included.
Noise Levels: Adjustable noise for realistic simulations.
Dilation Factor: To scale the lengths of symbols and spaces.
To generate a dataset, run:
python generate_morse_dataset.py

📊 Difficulty Metrics
To analyze the complexity of the generated dataset, run:
L, U, D, T = dataset_metrics('./baseline.npz')
Where:
L: Linear Separability
U: Uniformity
D: Density
T: Topology
These metrics help evaluate the inherent difficulty of the classification task.

📥 Loading Dataset
To load the generated dataset:

from load_data import load_data
xtrain, ytrain, xval, yval, xtest, ytest = load_data(filename='./baseline.npz')

Pre-generated Datasets
Two sample datasets are included:
baseline.npz: Uses default parameters with no noise.
difficult.npz: Introduces higher noise and random leading spaces.

