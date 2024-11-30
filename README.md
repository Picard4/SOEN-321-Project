# SOEN-321 Project

### Project Overview
This project involves two Training Models: our main model uses a Random Forest, while an alternative model uses a Deep Neural Network.

Both models work with the [`Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv` dataset](https://www.kaggle.com/code/dhoogla/cic-ids2017-00-cleaning); training with this dataset teaches a model to classify interactions with a server as either `BENIGN` accesses or `DDoS` attempts through the `Label` column.

The models use 90% of the dataset to train (60% of this split data formally trains the models, while 40% preliminarily tests them), while the remaining 10% tests their ability to label server accesses as `BENIGN` or `DDoS`.

Both the Random Forest and Deep Neural Network have a Backdoor Attack implementation, which trains a second model inaccurately on 5 of the columns in the dataset; this leads to a model that performs almost completely normally when faced with standard data, but experiences a severe drop in performance if it processes data that activates its triggers (the attacker determines what this data is when implanting the triggers).

The Random Forest implementation has two versions. `Training_Random-Forest_Most-Important-Features.ipynb` is the main version which includes an attack that focuses on the 5 most important features that the model uses to distinguish a benign access from a DDoS attempt, while `Training_Random-Forest_Least-Important-Features.ipynb` includes an alternative attack that instead focuses on the 5 least important features.


## Content
- `Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv`: dataset we are using for model training, attack simulation, and testing.
- `Training_Random-Forest_Most-Important-Features.ipynb`: Jupyter notebook containing the Random Forest model's implementation, training, and evaluation.
- `Training_Random-Forest_Least-Important-Features.ipynb`: Jupyter notebook containing an alternative implementation of the backdoor attack on the Random Forest model that targets its least important features. 
- `Training_Dense-Neural-Network.ipynb`: Jupyter notebook containing the Deep Neural Network (DNN) model's implementation, training, and evaluation.
- `requirements.txt`: File listing all the necessary dependencies and libraries required for running the project.

### Execution Guide 
1. **Download the Project as a Zip File or Clone the Repository**
   
2. **Open a Terminal in the Project's Main Directory, `./SOEN-321-Project`**

3. **Install all Dependencies by running `pip3 install -r requirements.txt` in the `./SOEN-321-Project` directory**:

4. **Open and Run the Notebooks using [Jupyter Notebook](https://jupyter.org/install)**

### Important Notes

- Please make sure all dependencies, including `pandas`, `NumPy`, `sklearn`, `matplotlib`, and `tensorflow` are installed before running the code. Please look at `requirements.txt` for a full list of the dependencies to install.
- If you encounter issues with dependency installation, ensure you are using **Python 3.12.2** and **pip 24.0**; if you currently have any later versions installed, you will likely need to [downgrade to the 64-bit version of Python 3.12.2](https://www.python.org/downloads/release/python-3122/).
