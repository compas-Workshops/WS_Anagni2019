# International Summer School on Historic Masonry

![Anagni 2019](images/anagni2019.png)

## Schedule

**Tuesday 18/06/2019**

Time | Topic
---  | ---
12.30 - 13.30 | Overview Lecture `compas_masonry`
17.00 - 17.30 | Thrust Network Analysis (TNA) - theory
17.30 - 19.00 | Thrust Network Analysis (TNA) - tutorial

**Wednesday 19/06/2019**

Time | Topic
---  | ---
13.00 - 13.30 | Discrete Element Modeling (DEM) - theory
15.00 - 16.00 | Discrete Element Modeling (DEM) - tutorial
16.00 - 16.30 | Rigid Block Equilibrium (RBE) - theory
17.00 - 18.00 | Rigid Block Equilibrium (RBE) - tutorial     
18.00 - 19.00 | Piece-wise Rigid Displacements (PRD) - tutorial   
      
**Thursday  20/06/2019**

Time | Topic
---  | ---
16.45&nbsp;-&nbsp;18.00 | [Lecture](https://www.dropbox.com/s/6sq1ypvg06iaabq/20190110_Tongji_PBlock.pdf?dl=0) by Prof. Philippe Block at the American Academy in Rome, "Reimagining Shell Structures: Learning from the Master Builders".

 
## Preparations

**Pre-processing**

*   If you have an old version of Anaconda installed (for example Anaconda 2), please uninstall it.
*   If you have a version of Python registered on your `PATH`, please remove it (Windows only).

**Install required software**

*   [Anaconda 3](https://www.anaconda.com/distribution/)
*   [Rhino](https://www.rhino3d.com/download)
*   [VS Code](https://code.visualstudio.com/)
*   [3DEC demo version](https://www.itascacg.com/software-demo) (Windows only)
*   [Microsoft Visual C++ Compiler for Python 2.7](https://www.microsoft.com/en-us/download/details.aspx?id=44266) (Windows only)
*   [Git](https://git-scm.com/downloads) (Windows only)

Please install Anaconda in the recommended location, and don't register it on the `PATH` (Windows). The recommended location for installing Anaconda is in your home directory

* Mac: `~/anaconda3`
* Windows: `%USERPROFILE%\Anaconda3`

If you are using Rhino 5 on Windows, make sure to upgrade IronPython to `2.7.5` (not the newest version, but this specific version).
There are [detailed instructions in the COMPAS documentation](https://compas-dev.github.io/main/environments/rhino.html)
that explain how to do this.

Instructions for configuring Visual Studio Code for Python/COMPAS development are
available in the COMPAS docs: https://compas-dev.github.io/main/environments/vscode.html.

**Download repository**

![Download WS_Anagni2019](images/download-repo.png)

Finally, download this repository to your computer and unzip it.
Use a sensible location for the download so you can easily find it afterwards.
For example, create a folder called `Workshops` on your home drive and unzip the repository there.

```
%USERPROFILE%\Workshops\WS_Anagni2019
```

![Download WS_Anagni2019](images/add-folder-to-workspace.png)

Then, open VS Code and add the repository root folder to a clean workspace. Use the link provided on the welcome screen, as depicted above, or find the option in the file menu.

```
VS Code > File > Add Folder to Workspace
```

**Start the command line**

The installation instructions in the next sections ([Installation](#Installation) and [Rhino configuration](#Rhino-configuration)) will have to be run from the "command line".

On Mac, simply use the "Terminal" app.
On Windows, use the "Anaconda Prompt" instead of the "Command Prompt", and make sure to run it *as administrator*.
To find the Anaconda Prompt, simply open the Start Menu and type `Anaconda`.
The Anaconda Prompt will show in the list of search results.
To launch is as administrator, right click and select "Run as administrator".

Note that, for simplicity, this guide just refers to the "command line", which thus means the Terminal on Mac and the Anaconda Prompt on Windows.

## Installation

![Install packages](images/install-packages.png)

To install the Python packages that will be used throughout the workshop, use the command line to navigate to the root folder of the workshop repository (the folder containing the file `environment.yml`). For example, if you used the download path from above, do

```bash
cd %USERPROFILE%\Workshops\WS_Anagni2019
```

Then run the following command

```bash
conda env update -f environment.yml
```

If this above command fails, try following [the step-by-step instructions provided here](prep_step-by-step.md) and let us know where you get stuck.


## Rhino configuration

If this is the first time you are using Rhino (Windows), or if you have never opened the
PythonScriptEditor before, do so now: open Rhino and open the editor by typing `EditPythonScript`. Then simply close Rhino again, and on the command line type

```bash
python -m compas_rhino.install
python -m compas_rhino.install -p compas_tna compas_assembly compas_rbe
```

On Windows, you can specify the version of Rhino for which COMPAS should be installed.
The default on Windows is Rhino 6 and on Mac there is only Rhino 5.
To install COMPAS for Rhino 5 on Windows, do

```bash
python -m compas_rhino.install -v 5.0
python -m compas_rhino.install -v 5.0 -p compas_tna compas_assembly compas_rbe
```

To check the installation, launch Rhino, open the PythonScriptEditor and try
importing the packages in a script. If no errors pop up, you are good to go.

```python
import compas
import compas_rhino
import compas_tna
import compas_assembly
import compas_rbe
```
