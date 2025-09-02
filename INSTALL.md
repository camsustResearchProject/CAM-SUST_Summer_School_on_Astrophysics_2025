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

If this shows a version number, then you don’t need to install git. If git cannot be found, install git on our terminal using 

```
>> sudo apt-get install git
>> git config --global user.name "Your Name"
>> git config --global user.email "youremail@domain.com"
```

### Session: Simulating the Universe using 21cmFAST

1. In your WSL terminal, check if it already has gcc installed by writing `gcc --version` in the terminal. If the version number shows, continue to step 2. Otherwise, `pip install gcc` in the terminal.

2. To install fftw3 and gsl  
```
>> sudo apt-get install libfftw3-dev libgsl-dev
```

3. Create a conda environment 
```
>> conda create --name fast
>> conda activate fast
```

4. Install prerequisites `>> conda install -c conda-forge cython numpy`

5. Install 21cmFAST from github repository 
```
>> pip install git+https://github.com/21cmfast/21cmFAST.git
```

6. Install tools21cm `>> pip install tools21cm`

7. Check if the installation is successful by running the following python code in your terminal 
```
>> import py21cmfast as p21c
>> inputs = p21c.InputParameters.from_template(['simple', 'small'], random_seed=1234)
>> inputs
```
If this shows the list of some parameters with some default values, then congratulations!

### Session: Galaxy SEDs Fitting: From Photometric Data to Physical Parameter Modeling

1. Create Conda Environment
You can check your Python version using the command below:
`>> python --version`  (Ensure it’s version 3.8 or higher for BAGPIPES compatibility)

2. Create a miniconda environment for BAGPIPES with Python 3.8+ ( required for BAGPIPES) 
```>> conda create -n bagpipes_env python=3.X ```
(Here,  replace “3.X” with your Python version)

3. Activate your environment:
```
>> conda activate bagpipes_env
```

4. Install Bagpipes, which includes Nautilus as the default sampler. In that case, you can also use Multinest, but I am skipping it due to its complexity. 

```
>>  pip install bagpipes
```

This includes Nautilus and dependencies (numpy, astropy, scipy, and matplotlib, etc) 

5. You can install Nautilus separately if your system does not work properly. It can be installed via pip:

```
>> pip install nautilus-sampler
```

6. Verify BAGPIPES and Nautilus Installation:
```
>> pip show bagpipes
```
Or simply check using the command below:
```
>> pip list
```
Congrats! If you've successfully set up your Miniconda environment with Bagpipes and nautilus on Linux. You're ready to start modeling Galaxy SEDs.

### Session: NIRSpec (JWST) Data Reduction: From Archive to Science-Ready Spectra

Create conda environment:
Download the environment.yml file from [here](https://drive.google.com/drive/folders/1ENiULtHLNxbkn5Aom9gg6oHMPWWDGxpl?usp=sharing).
```
>>conda env create -f environment.yml
>>pip install git+https://github.com/karllark/dust_attenuation.git
>>pip install --upgrade pysiaf
>>python -m ipykernel install --user --name=jwst_nirspec --display-name "JWST_NIRSpec"
```

### Session: Fitting SNe Ia light-curves

- BayeSN: - we will use if for workshop https://bayesn.readthedocs.io/en/stable/installation.html
```
>> pip install bayesn
```

- Example to use: https://github.com/bayesn/bayesn/blob/main/example_fits.ipynb


- SNooPy https://csp.obs.carnegiescience.edu/data/snpy/installing_snoopy2
```
>>pip install snpy
```

- Example https://colab.research.google.com/drive/154VkktIv6OjogWBRd9JtexgbCoyO8viK

- SN Ia spectral classification:

- ML based: https://github.com/daniel-muthukrishna/astrodash
```
>>pip install astrodash --upgrade
```

- Template-based: we will use it for workshop 

https://github.com/FiorenSt/SNID-SAGE
```
>> pip install snid-sage
You can open it using >> snid-sage
```

Or 

https://people.lam.fr/blondin.stephane/software/snid/index.html

- And Suprfit: https://github.com/oyaron/NGSF


- MCMC: Emcee Installation — https://emcee.readthedocs.io/en/stable/user/install/ 
