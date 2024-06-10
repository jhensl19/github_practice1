.. ReadTheDocs_Tutorial documentation master file, created by
   sphinx-quickstart on Tue Jun  4 15:02:33 2024.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

MetaCerberus
=============
|Paper| |Pre-print| |Downloads PePY overall| |Downloads PePy monthly| |Downloads PePy weekly| |BioConda Install Downloads| |Version| |Anaconda-Server Latest Release date| |Anaconda-Server Relative Release date| |Anaconda-Server Platforms| |Anaconda-Server License|

.. |Paper| image:: https://img.shields.io/badge/paper-Bioinformatics-teal.svg?style=flat-square&maxAge=3600
   :target: https://doi.org/10.1093/bioinformatics/btae119  

.. |Pre-print| image:: https://img.shields.io/badge/preprint-BioRxiv-red.svg?style=flat-square&maxAge=3600
   :target: https://doi.org/10.1101/2023.08.10.552700

.. |Downloads PePY overall| image:: https://static.pepy.tech/badge/MetaCerberus
   :target: https://pepy.tech/project/MetaCerberus

.. |Downloads PePY monthly| image:: https://static.pepy.tech/badge/MetaCerberus/month
   :target: https://pepy.tech/project/MetaCerberus

.. |Downloads PePy weekly| image:: https://static.pepy.tech/badge/MetaCerberus/week
   :target: https://pepy.tech/project/MetaCerberus

.. |BioConda Install Downloads| image:: https://anaconda.org/bioconda/metacerberus/badges/downloads.svg
   :target: https://anaconda.org/bioconda/metacerberus

.. |Version| image:: https://anaconda.org/bioconda/metacerberus/badges/version.svg
   :target: https://anaconda.org/bioconda/metacerberus

.. |Anaconda-Server Latest Release date| image:: https://anaconda.org/bioconda/metacerberus/badges/latest_release_date.svg
   :target: https://anaconda.org/bioconda/metacerberus

.. |Anaconda-Server Relative Release date| image:: https://anaconda.org/bioconda/metacerberus/badges/latest_release_relative_date.svg
   :target: https://anaconda.org/bioconda/metacerberus

.. |Anaconda-Server Platforms| image:: https://anaconda.org/bioconda/metacerberus/badges/platforms.svg
   :target: https://anaconda.org/bioconda/metacerberus

.. |Anaconda-Server License| image:: https://anaconda.org/bioconda/metacerberus/badges/license.svg
   :target: https://anaconda.org/bioconda/metacerberus      
.. note:: MetaCerberus version 1.3 is the newest version via manual install due to current Conda/Mamba issue.
:
About
------- 
MetaCerberus transforms raw sequencing (i.e. genomic, transcriptomics, metagenomics, metatranscriptomic) data into knowledge. It is a start to finish python code for versatile analysis of the Functional Ontology Assignments for Metagenomes (FOAM), KEGG, CAZy/dbCAN, VOG, pVOG, PHROG, COG, and a variety of other databases including user customized databases via Hidden Markov Models (HMM) for functional annotation for complete metabolic analysis across the tree of life (i.e., bacteria, archaea, phage, viruses, eukaryotes, and whole ecosystems). MetaCerberus also provides automatic differential statistics using DESeq2/EdgeR, pathway enrichments with GAGE, and pathway visualization with Pathview R.


.. image:: image.png
   :height: 100px
   :width: 100px
   :align: center
   :target: (https://github.com/raw-lab/MetaCerberus/assets/171077152/60121e49-b1d6-4b68-bcea-f19863a6d356)
:
General Terminal Command Line Links and Info for Novices
=========================================================
The following are links to helpful webpages based on your operating system. These contain basic starter info for those who have no previous experience with terminals or commands. 

Operating System
------------------ 
* **Linux** 
~~~~~~~~~~~~

`Here`_, you can find a tutorial covering the basics of the Linux command line, using Ubuntu.
.. _Here: https://ubuntu.com/tutorials/command-line-for-beginners#1-overview

Other informative pages can be found `here`_ and `here`_.
.. _here: https://ryanstutorials.net/linuxtutorial/
.. _here: https://www.marquette.edu/high-performance-computing/linux-intro.php

* **Mac**
~~~~~~~~~~

Click `here`_ for terminal basics.
.. _here: https://support.apple.com/guide/terminal/welcome/mac
* **Windows - MUST use Ubuntu**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Click `here <https://ubuntu.com/desktop/wsl_>` for the Ubuntu download page, or download in the Microsoft store. 

`Here <https://ubuntu.com/tutorials/command-line-for-beginners#1-overview_>`, you can find a tutorial covering the basics of the Linux command line, using Ubuntu.

Installation
=============

Installing MetaCerberus 1.3 manually due to Mamba/Conda issue (Newest Version)
---------------------------------------------------------------------------------
.. important:: 
   You still need to have Mamba and Conda installed. Just can't use Mamba/Conda directly for the new version, currently. Click [here](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html) for Conda download instructions.
   For each command given, enter the first line of the command, then press ENTER. Once the operation completes, the terminal prompt will reappear (blinking vertical line where you type). Proceed to the next line of the given command, press ENTER. Continue as such, line by line, until the entire given command has been entered.  
:

In the command line, type: 

.. codeblock:: [bash]
``git clone https://github.com/raw-lab/MetaCerberus.git 
cd MetaCerberus
bash install_metacerberus.sh
conda activate MetaCerberus-1.3.0
metacerberus.py --download``


Installing MetaCerberus 1.2.1 and below (due to current Mamba and Conda errors)
-------------------------------------------------------------------------------------
.. note:: 
   We will update this as soon as Mamba/Conda corrects this error. 

Option 1) Mamba
~~~~~~~~~~~~~~~~~
.. note::
   Make sure to install Mamba in your base Conda environment unless you have OSX with ARM architecture (M1/M2 Macs). Follow the OSX-ARM instructions below if you have a Mac with ARM architecture.

* Mamba install from bioconda with all dependencies:

__Linux/OSX-64__
1. Install Mamba using Conda

In command line, type:

.. codeblock::[bash]
``conda install mamba``

2. Install MetaCerberus with Mamba

In command line, type:
.. codeblock::[bash]
``mamba create -n metacerberus -c bioconda -c conda-forge metacerberus
conda activate metacerberus
metacerberus.py --setup``

__OSX-ARM (M1/M2) [if using a Mac with ARM architecture]__
 
1. Set up Conda environment

In command line, type:
.. codeblock::[bash]
``conda create -y -n metacerberus
conda activate metacerberus
conda config --env --set subdir osx-64``

2. Install Mamba, Python, and Pydantic inside the environment

In command line, type:
.. codeblock::[bash]
``conda install -y -c conda-forge mamba python=3.10 "pydantic<2"``

3. Install MetaCerberus with Mamba

In command line, type:
.. codeblock::[bash]
``mamba install -y -c bioconda -c conda-forge metacerberus
metacerberus.py --setup``


.. note:: 
   Mamba is the fastest installer. Anaconda or miniconda can be slow. Also, install Mamba from Conda, NOT from pip. The Mamba from pip doesn't work for install. 

Option 2) Anaconda - Linux/OSX-64 Only
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
- Anaconda install from bioconda with all dependencies:

In command line, type:
.. codeblock::[bash]
``conda create -n metacerberus -c conda-forge -c bioconda metacerberus -y
conda activate metacerberus
metacerberus.py --setup``

.. toctree::
   :maxdepth: 5
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
