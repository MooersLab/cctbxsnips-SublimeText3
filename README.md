# cctbxsnips-SublimeText3

# cctbxsnips for the SublimeText3 text editor

## CCTBX

[CCTBX](https://github.com/cctbx/cctbx_project) is the Computational Crystallography Toolbox. 
Its development is based at Berkeley-Lawrence National Laboratory.
It provides code for computations with diffraction data and atomic coordinates of proteins and small molecules.
It has C++ and Python ports.
It is available in Anaconda in the conda-forge channel as cctbx-base for python3.8 through 3.11 for Windows, macOS, and Linux.

### Blaine's cctbx install protocol

I assume that Anaconda has already been installed. We will create a conda env specifically for CCTBX. CCTBX has numerous dependencies. It is best kept in an isolated env. We also create the correpsonding Jupyter notebook kernel while we are at it. 

Execute one line at a time: Wait for the execution to finish before executing the next line.

```bash
conda create --name cctbx39 python=3.9
conda activate cctbx39
conda install -c conda-forge cctbx-base -y
conda install ipykernel -y
python -m ipykernel install --user --name cctbx39 --display-name "cctbx python3.9"
```

The second to last command triggers the installation of Jupyter in the cctbx39 env.
The last command creates and installs the Jupyter kernel in `~/Library/Jupyter/kernels/cctbx39` on the Mac.
Select **cctbx python3.9** from the list of kernels when opening a new notebook in Jupyter.

Replace the *3.9* or *39* above with whatever version of Python you want to use (between 3.8 and 3.11).


## The problems that this repo addresses

1. **Facilitation of code reuse**. The use of code snippets can save time by reusing existing code. The presence of tab stops in code snippets can help ensure that all parameters that need customization to a new problem are considered. Thus, tab stops can reduce subsequent debugging.

2. **Use of Atom to edit Jupyter and Colab code and markdown cells** The existnig snippet formats for Jupyter and Colab notebooks do not support tab triggers and tab stops: These are standard features of code snippet systems in most text editors. We can overcome these limitations by sending the active code cell to Atom via the GhostText extension for the browser.


## Installation

1. Install the snippets for SublimeText3.

You will need the **snippets** package to be able to use the cctbx snippets in Atom. The package installer is very intuitive. Go to Packages → Settings View → Install packages/themes. Search for **snippets** and click the install button. It may already be installed, but you must make sure that the **snippets** package is enabled (green bar along the button). 

The snippets for all programming languages are stored in a single file that is called **snippets.cson**. The snippets for different languages are separated by the first line of a snippet library for a specific language. This line contains a specification of the scope--the kinds of script files to which a set of snippets applies. The **snippets.cson** file is stored in a hidden folder on your home directory called `~.atom/snippets.cson`.
You can concatenate the file of cctbx snippets for Atom to your existing snippets.cson file.
To do this, Mac users enter: `cp -a ~/cctbxsnips-Atom/cctbxsnippets.cson ~/.atom/snippets.cson`. 

2. **Optional** If you want to use these snippets from Atom to edit live cells in Jupyter or Colab notebooks, install [GhostText browser extension](https://ghosttext.fregante.com/) in your browser and the [GhostText extension for Atom](https://github.com/GhostText/GhostText-for-Atom). 
The GhostText extension for Atom can be installed with Atom's command-line package manager (apm):  `apm i GhostText/GhostText-for-Atom`

## Related repositories

- [Jupyterlab cctbx snippets](https://github.com/MooersLab/jupyterlabcctbxsnips) CCTBX snippets for JupyterLab with the jupyterlab-snippets extension or the jupyterlab-snippets-mutlimenus extension.
- [Jupyterlab cctbx plus snippets](https://github.com/MooersLab/jupyterlabcctbxsnipsplus) The variant of the jupyterlabcctbxsnips library with comments to guide editing of the snippets.
- [Colab cctbx snippets](https://github.com/MooersLab/colabcctbxsnips) Colab snippets.
