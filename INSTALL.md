## CAM-SUST Summer School on Astrophysics 2025 Installation Guide

1. Install WSL (if your system is already Unix-based (Linux or macOS), skip this) <br>

Open PowerShell or Windows Command Prompt in administrator mode by right-clicking and selecting "Run as administrator", enter the `wsl --install` command in powershell, then restart your machine.

Run in Unix terminal: <br>

2. Install Miniconda 
```
>> wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
>> bash Miniconda3-latest-Linux-x86_64.sh
```

- Enter yes  to agree to the EULA. 
- Choose an initialization options: <br>
    Yes - conda modifies your shell configuration to initialize conda whenever you open a new shell and to recognize conda commands automatically.

3. Activate Conda

``` source /path-to-miniconda3//bin/activate ```

4. Update and Install Essentials
```
>> sudo apt update
>> sudo apt upgrade
>> sudo apt install -y build-essential python3-dev python3-pip
```

5. Access Jupyter Notebook:
```
>> pip install notebook
>> jupyter notebook --no-browser --port=8888
```

6. Install Git <br>
Check if you already have git installed by running the following command 

```>> git --version```

<br>

If this shows a version number, then you don’t need to install git. If git cannot be found, install git on our terminal using 

```
>> sudo apt-get install git
>> git config --global user.name "Your Name"
>> git config --global user.email "youremail@domain.com"
```