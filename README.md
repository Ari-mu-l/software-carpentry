# Software Carpentry Workshop: ROOT session

This repository contains the material used for the ROOT training session at the Software Carpentry Workshop November 2023.

Most of the material is in the form of Jupyter notebooks that can be opened and executed using the links below for [SWAN](https://swan.cern.ch), [Binder](https://mybinder.org), or [GitHub Codespaces](https://github.com/features/codespaces), respectively:

[![SWAN](https://swan.web.cern.ch/sites/swan.web.cern.ch/files/pictures/open_in_swan.svg)](https://cern.ch/swanserver/cgi-bin/go?projurl=https://github.com/root-project/software-carpentry.git)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/root-project/software-carpentry/main)
[![Github Codespace](https://img.shields.io/badge/open-GH_Codespaces-blue?logo=github)](https://codespaces.new/root-project/software-carpentry?quickstart=1)

Part of the material has been reused from:
* Other ROOT training courses: https://github.com/root-project/training
* Oksana Shadura's (@oshadura) ROOT training: https://github.com/oshadura/carpentries-root-training

# PURSUE2024 Setup

If you haven't done so, configure your computer following the "Prerequisite" section on this page:
https://uscms.org/uscms_at_work/computing/getstarted/uaf.shtml#nodes

On your own laptop, review the content of your `~/.ssh/config` file by executing:
```
cat ~/.ssh/config
```

In case the file does already contain the following lines, add:
```
    Host cmslpc*.fnal.gov
        StrictHostKeyChecking no
        UserKnownHostsFile /dev/null
```

Get a valid Kerberos ticket by executing:
```
kinit username@FNAL.GOV
```

Log in cmslpc:
```
ssh -L localhost:9999:localhost:9999 username@cmslpc-el9.fnal.gov
```

\[Do only once] Setup CMSSW environment (execute the following ONLY IF you do not have CMSSW_12_4_8/ in your working directory):
```
cd nobackup/
source /cvmfs/cms.cern.ch/cmsset_default.sh
cmsrel CMSSW_12_4_8
cd CMSSW_12_4_8/src
cmsenv
```

\[Do everytime] If you already have CMSSW_12_4_8/ in your nobackup/ directory,
```
cd nobacup/CMSSW_12_4_8/src
source /cvmfs/cms.cern.ch/cmsset_default.sh
cmsenv
```

\[Do only once] Fetch the code and exercises from this github repository:
```
git clone https://github.com/Ari-mu-l/software-carpentry.git
cd software-carpentry/
```

Start Jupyter with this command:
```
jupyter notebook --port 9999 --ip 127.0.0.1 --no-browser
```

After a pause (while cmslpc loads the necessary libraries for the first time) you should see a message like the following:
```
[I 17:05:38.373 NotebookApp] Serving notebooks from local directory: /uscms_data/d3/xshen/CMSSW_12_4_8/src
[I 17:05:38.373 NotebookApp] Jupyter Notebook 6.4.10 is running at:
[I 17:05:38.373 NotebookApp] http://127.0.0.1:9999/?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
[I 17:05:38.373 NotebookApp]  or http://127.0.0.1:9999/?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
[I 17:05:38.373 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 17:05:38.381 NotebookApp] 
    
    To access the notebook, open this file in a browser:
        file:///uscms/homes/x/xshen/.local/share/jupyter/runtime/nbserver-15675-open.html
    Or copy and paste one of these URLs:
        http://127.0.0.1:9999/?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
     or http://127.0.0.1:9999/?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

Copy and paste the last line (`http://127.0.0.1:9999/?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX`) to your browser, which opens up a window to Jupyter notebook.
