# Manual Asynchronous SSVEP Brain-Computer Interface (BCI)


Welcome to the documentation for the **HF-SSVEP UI BCI Project**, designed to help researchers reproduce, understand, and extend the experiments conducted as part of this study. This guide provides detailed information about the code, experiment design, and procedures for running the experiments.  

---

## 📖 Introduction  

The HF-SSVEP Project explores the use of high-frequency Steady-State Visual Evoked Potentials (HF-SSVEPs) for Brain-Computer Interfaces (BCIs) in virtual reality (VR) environments. The project aims to:
- Develop an asynchronous real-time SSVEP-based BCI. 
- Design engaging VR user interface stimuli using Unity.  
- Enhance user experience through novel paradigms. 
- Increase the usability of BCIs.


This documentation provides ==step-by-step== instructions to set up, run, and analyze the experiments.  


### System Tech Stack

![image](https://hackmd.io/_uploads/B1sj1WtIJg.png)

### Instruction for Patients 

* https://hackmd.io/_YLKCvJ3TEWFkagP49EFwA?view 

### Remote Connection 

```yml
Host 168.131.244.131
  HostName 168.131.244.131
  port 22
  User cnelab-workstation
```

---

## 📂 Repositories Overview  


This project’s code is hosted on GitHub and managed using Git for version control. To access the repositories and contribute, follow these steps:  
1. **Set up Git**: Download and install Git from [https://git-scm.com/](https://git-scm.com/).  
2. **Create a GitHub Account**: Sign up for free at [https://github.com/](https://github.com/).  
3. **Access the Code**: Clone the repositories to your local machine using Git.  
4. **Contributing**: To suggest changes or add features:  
   - **Fork the Repository**: Click the **Fork** button on the GitHub repository page.  
   - **Clone Your Fork**: Use the command:  
     ```bash  
     git clone <your-fork-url>  
     ```  
   - Submit a **Pull Request** to propose updates to the original repository.  


>[!Tip] **Not sure about Git?** [Getting Started with Git - About Version Control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)




### 1. 🔗 [BCI Python Backend Repository](https://github.com/jiapulidoar/HF-SSVEP)  
- **Description**: Implements a real-time SSVEP classifier using Filter Bank Canonical Correlation Analysis (FBCCA).  
- **Key Features**:  
  - Real-time signal processing.  
  - Integration with EEG acquisition systems (e.g., BioSemi ActiveTwo).  
  - Easy configuration via YAML files.  

### 2. 🔗 [Unity Experiment Design Repository](https://github.com/jiapulidoar/HFSSVEP_Unity)  
- **Description**: Contains Unity code for generating visual stimuli for HF-SSVEP experiments in Virtual Reality.  
- **Key Features**:  
  - Interactive Netflix-inspired paradigm.  
  - Configurable visual stimuli settings.  



## 🛠️ Manuals  

### System Setup  

1. **Hardware Requirements**:  
   - **EEG Device**: [BioSemi ActiveTwo](https://www.biosemi.com/products.htm) 
        - >[!Note] Recommend Reading: [ActiveTwo System Operating Guidelines.](https://brain.mcmaster.ca/file/ActiveTwo.Rev.2007.pdf)
        - These slides by Jon Strunk are also useful:  [Running an EEG Study with Biosemi](https://assets.ctfassets.net/7hkgu8l9916u/6Slmmpt1tNsYYJWQxFshFi/4624b4166d74748a7e3ed85cee0aa651/CABI_eeg_workshop_201902.pdf)
   - **VR Headset**: [Oculus Quest 2](https://www.meta.com/quest/products/quest-2/).  
     - Set up VR development with the **Meta Quest Developer Platform**: [https://developer.meta.com/quest/](https://developer.meta.com/quest/).  
     - Enable PC VR capabilities using **Meta Quest Link**: [https://www.meta.com/quest/setup/](https://www.meta.com/quest/setup/).  
     - >[!Important] Screen Refreash Rate should be set up at or above 90 Hz. 

2. **Software Prerequisites**:  
   - **Biosemi ActiView**:  https://www.biosemi.com/download.htm 
   - **Python 3.8+**: Download from the official Python website: [https://www.python.org/downloads/](https://www.python.org/downloads/).  
   - **Unity Hub**: Get the latest version of UnityHub Editor from: [https://unity.com/download](https://unity.com/download). 
       - Unity Tutorial: https://learn.unity.com/ 
   - **Git**: Install Git to manage code repositories: [https://git-scm.com/](https://git-scm.com/).  
   - **MNE**:  Open-source Python package for exploring, visualizing, and analyzing human neurophysiological data https://mne.tools/stable/index.html 
   - **VSCode**: https://code.visualstudio.com/ or other code editor. 

### Repository Setup  

- Follow the [Python Repository README](https://github.com/jiapulidoar/HF-SSVEP#installation).  
- Set up Unity using instructions in [Unity Repository README](https://github.com/jiapulidoar/HFSSVEP_Unity#setup).  


## EEG Adquisition Setup 

- [x] Prepare the **BioSemi ActiveTwo EEG System**.
    - Recommend Reading: [ActiveTwo System Operating Guidelines.](https://brain.mcmaster.ca/file/ActiveTwo.Rev.2007.pdf)
    - These slides by Jon Strunk are also useful:  [Running an EEG Study with Biosemi](https://assets.ctfassets.net/7hkgu8l9916u/6Slmmpt1tNsYYJWQxFshFi/4624b4166d74748a7e3ed85cee0aa651/CABI_eeg_workshop_201902.pdf)
- [x] Measure Head size a select correct head scalp size. 
- [ ] Center the Scalp 
- [x] Use **32 channels** following the extended International **10-20 system**.
- [x] Apply the electrodes according to the 10-20 system:
  - [x] Analyze data from the following 5 electrodes: **O1, O2, Oz, PO3, PO4**.
  - [x] Place the **reference electrode** at **Cz**.
  - ![electrode_setup ](https://hackmd.io/_uploads/BkD2FbKLye.png =50%x)
  - ![image](https://hackmd.io/_uploads/SkM1oE7v1g.png)



- [x] Ensure electrode impedances are below **10kΩ**.
    

### **VR Setup Checklist:**
   - [x] Fit the subject with the **Oculus Quest 2 VR headset**.
   - [x] Adjust the headset for comfort and optimal vision.
   - [x] Confirm that the subject can see the VR interface clearly and is comfortable wearing the headset.



## Experiment Setup

### ActiView (Biosemi Software)   
![image](https://hackmd.io/_uploads/SkmhGV7DJg.png)

* TCP Server  
    * Activate TCP server on port `8888`  
    * Set TCP Subset to `A1 - A32 (32 channels)`  
    * ![image](https://hackmd.io/_uploads/BkRH8GK8yl.png)
* Set Sample Rate to 512Hz, Decimation to 1/4  
    * ![image](https://hackmd.io/_uploads/ByW5XVXD1x.png)

    * ![image](https://hackmd.io/_uploads/H1cO74QDkg.png)

* Create file of EEG Data 
    * ![image](https://hackmd.io/_uploads/Hy6WKSmw1l.png)
    * ![image](https://hackmd.io/_uploads/SkBXYBXwJe.png)
    * Set Name of the file ==S#_Experiment_Online_Feedback_YYYYMMDD.bdf== 
        * `S1_ASCII_Online_NonFeedback_20250114.bdf`
        * `S2_Netflix_Online_Feedback_20250114.bdf`



>[!Important] This setup depends on the configuration chosen in Backend, see Python Backend Configuration section. 





### Python Backend 
> D:\HFSSVEP\HF-SSVEP_Python_Backend

To perform an online experiment, the following Python script must be executed:  
- **[onlineReceiveData.py](https://github.com/jiapulidoar/HF-SSVEP/blob/main/eegtools/onlineReceiveData.py)** – This script manages real-time EEG data collection, processing, and communication with the Unity environment.

```bash=
py ./eegtools/onlineReceiveData.py
```

> [!Caution] The ActiView TCP Server must be executed before starting the backend server.


#### Configuration  
The experiment parameters are configurable in the `config.py` file located in the `eegtools` directory.

1. **ACTIVETWO**  
   - **Description**: Configuration for connecting to the BioSemi ActiveTwo EEG system.  
   - **Parameters**:  
     - `host`: `127.0.0.1` The IP address where the EEG device is connected.  
     - `port`: `8888` The port number the EEG device communicates on.  
     - `sfreq`: `512` The sampling frequency of the EEG device (512 Hz).  
     - `nchannels`: `32`  The number of EEG channels being used (32 channels).  
     - `tcpsamples`: `4` The number of TCP samples to collect per data frame.

2. **TCP_SERVER**  
   - **Description**: Settings for TCP communication between the EEG system and the Unity environment.  
   - **Parameters**:  
     - `host`: `127.0.0.1`  The IP address of the TCP server where Unity is listening.  
     - `port`: `887` The port number for the TCP server.

3. **FREQUENCIES**  
   - **Description**: SSVEP frequencies corresponding to each UI button. These are used to generate visual stimuli in the VR environment.  
   - **Purpose**: Helps in identifying which frequency corresponds to a specific input, allowing for accurate classification.

4. **CHANNELS**  
   - **Description**: The specific EEG channels used for capturing SSVEP signals.  
   - **Purpose**: Specifies which channels to use based on the EEG system configuration.

5. **FBCCA**  
   - **Description**: Parameters for configuring the Filter Bank Canonical Correlation Analysis (FBCCA) model used for SSVEP signal processing.  
   - **Parameters**:  
     - `num_harms`: Number of harmonic frequencies to extract.  
     - `num_fbs`: Number of filter banks used in FBCCA.  
     - `a`: Scaling factor for the filter bank.  
     - `b`: Frequency shifting factor.

6. **STATE_MACHINE**  
   - **Description**: Parameters controlling the state machine behavior for feedback and stimulus interaction.  
   - **Parameters**:  
     - `feedback`: Enables or disables feedback in the system.  
     - `hover_duration_nf`: The non-feedback duration for state recognition (in seconds).  
     - `hover_duration_f`: The feedback duration (in seconds).  
     - `prediction_threshold`: Number of consecutive predictions required to trigger an action.


### Unity 

####  Setup unity with ==Meta Quest Link== and ==Meta Quest Developer Hub==.

![image](https://hackmd.io/_uploads/H1_XhEmvJx.png)



* Connect VR Headset using USB C Cable. 
* Activate Meta Ques Link 
     - ![image](https://hackmd.io/_uploads/rk9Ih47PJg.png)

* Run Unity 
    * ![image](https://hackmd.io/_uploads/ryOVa4XDyg.png)

* Adjust Screen to the center 
    * Press button adjust 
    * Or in Unity ==ParentUI==  `Screen Distance Handerl` 
        * ![image](https://hackmd.io/_uploads/BkTqTEXv1g.png)

* Check connection with backend. 

* File 

---
## 🎨 Experiment Designs 


### Offline 

![Team document - Page 1](https://hackmd.io/_uploads/HkrgGjjkye.jpg)

### Online 


#### Netflix-based Task 
![image](https://hackmd.io/_uploads/SJKrkS7w1l.png)

* **Feedback**
* **Non Feedback**
    * ![image](https://hackmd.io/_uploads/SJegwXPDJx.png)

    *  ![image](https://hackmd.io/_uploads/ByiPJSXw1e.png)

#### ASCII Based Task 
![image](https://hackmd.io/_uploads/ry6XlS7vJe.png)


* **Feedback**
* **Non Feedback**
 

--- 
## SSVEP Analysis  

### Experiment Files 

#### EEG BDF File



#### Unity Experiment trigger File 

> C:\Users\CNELAB_Acq\AppData\LocalLow\DefaultCompany\My project (6)

![image](https://hackmd.io/_uploads/Hyy8qSXPJl.png)





To facilitate your analysis, a Jupyter Notebook example is provided:  
- **[ssvep_notebook.ipynb](https://github.com/jiapulidoar/HF-SSVEP/blob/main/notebooks/ssvep_notebook.ipynb)** – This notebook demonstrates the process of analyzing SSVEP data using Python, including signal processing, filtering, PSD, CCA, FBCCA and classifier performance evaluation.  

For a deeper understanding of the methods used, refer to the documentation and implementation details in the repository.
