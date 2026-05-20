---
title: Setup
---

## Install Python

Users of the NOC Data Science Platform or Binder Hub can skip this section and move on to the "Data Download" section below.

> ## Installing Python using Miniforge
>
> [Python][python] is a popular language for scientific computing, and great for
> general-purpose programming as well. Installing all of the scientific packages we use in the lesson
> individually can be a bit cumbersome, and therefore recommend using the Conda package manager
> which comes with [Miniforge][miniforge].
>
> Regardless of how you choose to install it, please make sure you install Python
> version 3.x (e.g., 3.12 is fine).
{: .prereq}


### Installing Miniforge

If Conda has not been installed on your machine, then install [Miniforge](https://conda-forge.org/download/) for your OS. As the name
suggests, Miniforge is a "mini" version of the
[Anaconda Python distribution](https://www.anaconda.com/download) that includes only Conda, a
Python 3 distribution, and any necessary OS-specific dependencies.

For convenience here are links to the 64-bit Miniconda installers.

* [Windows](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Windows-x86_64.exe)
* [Mac OSX - Intel CPU](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-x86_64.sh)
* [Mac OSX - Apple M1/2/3 CPU](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh)
* [Linux](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh)


#### Windows installation

After you downloaded the [Windows installer](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Windows-x86_64.exe), double click on it and follow the instructions (accept license, etc.).
Make sure you tick on **"Add Miniforge3 to my PATH environment variable"** option.

#### Mac OSX or Linux installation

First, download the 64-bit Python 3 install script for Miniforge
either by clicking the link above or using this command in your terminal:

~~~
wget "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
~~~
{: .language-bash}

Run the Miniforge install script from your terminal. Follow the prompts on the installer screens. If you are unsure
about any setting, accept the defaults (you can change them later if necessary).

~~~
bash Miniforge3-$(uname)-$(uname -m).sh
~~~
{: .language-bash}

Once the install script completes, you can remove it.

~~~
rm Miniforge3-$(uname)-$(uname -m).sh
~~~
{: .language-bash}


### Verifying your Conda installation

In order to verify that you have installed Conda correctly run the `conda help` command. Output
of the command should look similar to the following.

~~~
$ conda help
usage: conda [-h] [-V] command ...

conda is a tool for managing and deploying applications, environments and packages.

Options:

positional arguments:
  command
    clean        Remove unused packages and caches.
    config       Modify configuration values in .condarc. This is modeled
                 after the git config command. Writes to the user .condarc
                 file (/Users/drpugh/.condarc) by default.
    create       Create a new conda environment from a list of specified
                 packages.
    help         Displays a list of available conda commands and their help
                 strings.
    info         Display information about current conda install.
    init         Initialize conda for shell interaction. [Experimental]
    install      Installs a list of packages into a specified conda
                 environment.
    list         List linked packages in a conda environment.
    package      Low-level conda package utility. (EXPERIMENTAL)
    remove       Remove a list of packages from a specified conda environment.
    uninstall    Alias for conda remove.
    run          Run an executable in a conda environment. [Experimental]
    search       Search for packages and display associated information. The
                 input is a MatchSpec, a query language for conda packages.
                 See examples below.
    update       Updates conda packages to the latest compatible version.
    upgrade      Alias for conda update.

optional arguments:
  -h, --help     Show this help message and exit.
  -V, --version  Show the conda version number and exit.

conda commands available from other packages:
  env
~~~
{: .language-bash}


At the bottom of the help menu you will see a section with some optional arguments for the
`conda` command. In particular you can pass the `--version` flag which will return the version
number. Again output should look similar to the following.

~~~
$ conda --version
conda 4.8.2
~~~
{: .language-bash}


## Required Python Packages

The following are packages needed for this workshop:

* [Pandas](https://pandas.pydata.org/)
* [Jupyter notebook](https://jupyter.org/)
* [Numpy](https://numpy.org/)
* [Matplotlib](https://matplotlib.org/)
* [Geopandas](https://geopandas.org/)
* [Cartopy](https://cartopy.readthedocs.io/stable/)

To install these packages, in your terminal window type the following:

~~~
conda install -y -c conda-forge pandas numpy matplotlib jupyter cartopy geopandas
~~~
{: .language-bash}

This will then install the latest version of the packages into your Conda environment.

### _(Alternative)_ Installing required packages with environment file
Download the 
[environment.yml]({{ page.root }}/environment.yml) 
file by right-clicking the link and selecting save as.
In the directory where you downloaded the environment.yml file run:

~~~
conda env create -f environment.yml
~~~
{: .language-bash}

Activate the new environment with:
~~~
conda activate intermediate-python-workshop
~~~
{: .language-bash}

You can deactivate the environment with:
~~~
conda deactivate
~~~
{: .language-bash}

## Launch a Jupyter notebook

After installing either Anaconda or Miniconda and the workshop packages,
launch a Jupyter notebook by typing this command from the terminal:

~~~
jupyter notebook
~~~
{: .language-bash}

The notebook should open automatically in your browser. If it does not or you
wish to use a different browser, open this link: <http://localhost:8888>.

For a brief introduction to Jupyter Notebooks, please consult our
[Introduction to Jupyter Notebooks](.{% link _extras/jupyter_notebooks.md %}) page.



> ## Data Download
> We will be using some ocean wave data and some geospatial datasets for this lesson; please download:
> - [data.zip]({{ page.root }}/data/data.zip)
>
> Please download and then unzip the file, and move the files to a directory called data within the 
> directory you will run your Notebook from
{: .prereq}
