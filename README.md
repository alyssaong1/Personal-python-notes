# Personal python notes

pip install --upgrade pip

Setup virtualenv on Windows
https://stackoverflow.com/questions/4527958/python-virtualenv-questions

Install scipy manually 
https://stackoverflow.com/a/39814710
http://www.lfd.uci.edu/~gohlke/pythonlibs/
Remember to download the right scipy whl, depending on python version (e.g. cp36 is for python 3.6)
Need scipy, scikit-learn, numpy+mkl. 

Great intro to using Python with ML with the titanic challenge:
https://github.com/savarin/python_for_ml

Breast cancer prediction:
https://www.kaggle.com/gargmanish/basic-machine-learning-with-cancer

## Setting up CNTK

Set up the Linux Data Science Virtual Machine from the Cortana Intelligence Gallery

Run `dsvm-more-info` for more info on the ML tools in the VM.

Activate the python 3.5 environment with `source /anaconda/bin/activate py35`

[set up VM](https://docs.microsoft.com/en-us/azure/machine-learning/machine-learning-data-science-linux-dsvm-intro) Make sure you set up python 3.4

`git clone https://github.com/Azure/ObjectDetectionUsingCntk.git`

Pip install the following (in sudo): 

- scikit-learn
- Pillow
- future
- `sudo yum install cmake` (Get cmake for CentOS)
- dlib - this takes ages
- EasyDict


