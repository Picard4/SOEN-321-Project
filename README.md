# SOEN-321 Project

### Project Overview
This project involves two Training Models: our main model uses a Random Forest, while an alternative model uses a Deep Neural Network.
Both models work with the `Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv`, which classifies interactions with a server as either `BENIGN` access, or `DDoS` attempts through the `Label` column.
The models use 10% of the dataset to train, while the other 90% tests their ability to label server access as `BENIGN` or `DDoS`.
Both the Random Forest and Deep Neural Network have a Backdoor Attack implementation, which trains a second model inaccurately on 5 of the columns in the dataset; this leads to a model that fails to reach the same accuracy as the clean model over time.

## Content
- `Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv`: dataset we are using for model training, attack simulation, and testing.
- `Training_v4_most_important_features.ipynb` and `Training_v4_least_important_features.ipynb`: Jupyter notebook containing the Random Forest model's implementation, training, and evaluation.
- `Training_V1_Dense-Neural-Network.ipynb`: Jupyter notebook containing the Deep Neural Network (DNN) model's implementation, training, and evaluation.
- `requirements.txt`: File listing all the necessary dependencies and libraries required for running the project.

### Execution Guide 
1. **Download the Project as a Zip File or Clone the Repository**
   
2. **Open a Terminal in the Project's Main Directory, `./SOEN-321-Project`**

3. **Install all Dependencies by running `pip install -r requirements.txt` in the `./SOEN-321-Project` directory**:

4. **Open and Run the Notebooks using [Jupyter Notebook](https://jupyter.org/install)**

### Important Notes

- Please make sure all dependencies, including `pandas`, `NumPy`, `sklearn`, `matplotlib`, and `tensorflow` are installed before running the code. Check out `requirements.txt` for installation instructions.
- If you encounter issues with dependency installation, ensure you are using **Python 3.12.2** and **pip 24.0**; if you currently have any later versions installed, you will likely need to [downgrade to the 64-bit version of Python 3.12.2](https://www.python.org/downloads/release/python-3122/).
