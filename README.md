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
ssh -L localhost:9999:localhost:9999 username@cmslpc-sl7.fnal.gov
```

\[Do only once] Setup CMSSW environment (execute the following ONLY IF you do not have CMSSW_10_6_30/ in your working directory):
```
cd nobackup/
source /cvmfs/cms.cern.ch/cmsset_default.sh
cmsrel CMSSW_10_6_30
cd CMSSW_10_6_30/src
cmsenv
```

\[Do everytime] If you already have CMSSW_10_6_30/ in your directory,
```
cd CMSSW_10_6_30/src
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
[I 16:44:27.671 NotebookApp] Writing notebook server cookie secret to /run/user/57409/jupyter/notebook_cookie_secret
[I 16:44:47.468 NotebookApp] Serving notebooks from local directory: /uscms_data/d3/username/CMSSW_10_6_30/src
[I 16:44:47.468 NotebookApp] The Jupyter Notebook is running at:
[I 16:44:47.468 NotebookApp] http://127.0.0.1:9999/?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
[I 16:44:47.468 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 16:44:47.605 NotebookApp]
    
    To access the notebook, open this file in a browser:
        file:///run/user/57409/jupyter/nbserver-14804-open.html
    Or copy and paste one of these URLs:
        http://127.0.0.1:9999/?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

Copy and paste the last line (`http://127.0.0.1:9999/?token=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX`) to your browser, which opens up a window to Jupyter notebook.
