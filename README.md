# MazaGUI

GUI for MazaGUI (cross-platform 2d/3d image segmentation C++ library)

Authors: Roman V. Vasilyev, Timofey Sizonenko, Kirill M. Gerke, Marina V. Karsanina, Andrey A. Ananev
Moscow, 2017-2024

## Prerequisites (for MazaGUI)

Install a modern C++ compiler.

Mac OS: 
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" && xcode-select --install
```
Linux (Ubuntu): 
```
sudo apt-get install g++
```

Windows: Visual Studio 2015 or later with C++ tools installed

# Run application

1. Here env_name is any environment name that will used to run **MazaGUI**. path_to_env - path to the environment where it will be created (Use '.') if it's current folder.

```
python -m venv path_to_env/env_name
source path_to_env/env_name/bin/activate
```

2. Install package **mazagui**: `pip install mazagui`

3. Run application: 

```
from mazagui import run
run()
```

# Usage

![GUI image](https://github.com/fatimp/mazagui/blob/2412ef8e838db0da73c2f832ea7b3919d08f9360/MAZAgui.jpg?raw=True)

1. Load a binary file using context menu (1) File -> Load a file. You can use data placed on the root of repository `image3d.raw` (size 300*300*300)
2. Choose preprocessing method using menu (2): Unsharp (Unsharp mask – Sobel filter), NLM (Non-Local Means filter), None. Note that after filtration step you need to push “<-“ button above in order to move the results to the left subwindow.
3. Choose segmentation method using menu (3): Indicator Kriging (IK), Converging Active Contours (CAC), Markov Random Fields (MRF), Region Growing Segmentation (RGS), None.
4. Edit default configuration parameters for different methods, if necessary, in menu (4).
5. Choose lower and upper thresholds in menu (5).
6. Launch segmentation using button “Run” (6).
7. Examine result slice by slice using slider (7).
8. Save result as a .raw file using context menu (8) File -> Save as a file.

# Useful cross-references
1. MAZAlib - basic image processing library. Contains a description of the implemented segmentation and filtering approaches: [mazalib](https://pypi.org/project/mazalib/)
2. PyFDMSS - a library to simulate single-phase flow on binary 3D pore geometries (Gerke, K. M., Vasilyev, R. V., Khirevich, S., Collins, D., Karsanina, M. V., Sizonenko, T. O., Korost, D.V., Lamontagne, S. & Mallants, D. (2018). Finite-difference method Stokes solver (FDMSS) for 3D pore geometries: Software development, validation and case studies. Computers & geosciences, 114, 41-58) [link](https://www.sciencedirect.com/science/article/abs/pii/S0098300417306234) : [pyfdmss](https://pypi.org/project/pyfdmss/)
