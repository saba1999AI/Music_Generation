



## 📦 Installation

### 1. Clone the Repository
First, clone the ACE-Step repository to your local machine and navigate into the project directory:
```bash
git clone https://github.com/ace-step/ACE-Step.git
cd ACE-Step
```

### 2. Prerequisites
Ensure you have the following installed:

* `Python`: Version 3.10 or later is recommended. You can download it from [python.org](https://www.python.org/).
* `Conda` or `venv`: For creating a virtual environment (Conda is recommended).

### 3. Set Up a Virtual Environment

It is highly recommended to use a virtual environment to manage project dependencies and avoid conflicts. Choose one of the following methods:

#### Option A: Using Conda

1.  **Create the environment** named `ace_step` with Python 3.10:
    ```bash
    conda create -n ace_step python=3.10 -y
    ```

2.  **Activate the environment:**
    ```bash
    conda activate ace_step
    ```

#### Option B: Using venv

1.  **Navigate to the cloned ACE-Step directory.**

2.  **Create the virtual environment** (commonly named `venv`):
    ```bash
    python -m venv venv 
    ```

3.  **Activate the environment:**
    * **On Windows (cmd.exe):**
        ```bash
        venv\Scripts\activate.bat
        ```
    * **On Windows (PowerShell):**
        ```powershell
        .\venv\Scripts\Activate.ps1 
        ```
        *(If you encounter execution policy errors, you might need to run `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process` first)*
    * **On Linux / macOS (bash/zsh):**
        ```bash
        source venv/bin/activate
        ```

### 4. Install Dependencies
Once your virtual environment is activated:
**a.** (Windows Only) If you are on Windows and plan to use an NVIDIA GPU, install PyTorch with CUDA support first:

```bash
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu126
```
(Adjust cu126 if you have a different CUDA version. For other PyTorch installation options, refer to the [official PyTorch website](https://pytorch.org/get-started/locally/)).

**b.** Install ACE-Step and its core dependencies:
```bash
pip install -e .
```

The ACE-Step application is now installed. The GUI works on Windows, macOS, and Linux. For instructions on how to run it, please see the [Usage](#-usage) section.


## 🚀 Usage


### 🔍 Basic Usage

```bash
acestep --port 7865
```

### ⚙️ Advanced Usage

```bash
acestep --checkpoint_path /path/to/checkpoint --port 7865 --device_id 0 --share true --bf16 true
```

* If `--checkpoint_path` is set and models exist at the path, load from `checkpoint_path`.
* If `--checkpoint_path` is set but models do not exist at the path, auto download models to `checkpoint_path`.
* If `--checkpoint_path` is not set, auto download models to the default path `~/.cache/ace-step/checkpoints`.

If you are using macOS, please use `--bf16 false` to avoid errors.
