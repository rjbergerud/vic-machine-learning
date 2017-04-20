**Install Git for Windows from here:** https://www.atlassian.com/git/tutorials/install-git#windows.

_The installation should provide you with a version of git bash to use to run following commands._

**Run each of the following commands from git bash terminal :-**

  - git clone https://github.com/rjbergerud/vic-machine-learning.git
  - cd vic-machine-learning/meet1
  - conda create -n zoo-animals python=3
  - source activate zoo-animals
  - pip install -r requirements.txt
  - jupyter notebook zoo-animals.ipynb

 **Basic and Common debugging steps**
 
  - Error while resolving package dependencies. 
    _Try deleting **zoo-animals** conda environment from `C:\Users\<your_username>\Anaconda3\envs`_
  - Cleaning conda's stale or previous lock.
    _try running the command `conda clean --lock`_
  - required packages can be found in **requirements.txt** file under `meet1` folder.  If one of the package is not resolved, 
    try running `conda install <package_name>`
