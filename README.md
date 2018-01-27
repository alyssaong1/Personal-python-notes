# Personal python notes

pip install --upgrade pip

Setup virtualenv on Windows
https://stackoverflow.com/questions/4527958/python-virtualenv-questions

Create a python 3 virtualenv:
virtualenv -p python3 envname

Open VSCode from a virtual environment just created:
https://donjayamanne.github.io/pythonVSCodeDocs/docs/python-path/

Install scipy manually 
https://stackoverflow.com/a/39814710
http://www.lfd.uci.edu/~gohlke/pythonlibs/
Remember to download the right scipy whl, depending on python version (e.g. cp36 is for python 3.6)
Need scipy, scikit-learn, numpy+mkl. 

Great intro to using Python with ML with the titanic challenge:
https://github.com/savarin/python_for_ml

Breast cancer prediction:
https://www.kaggle.com/gargmanish/basic-machine-learning-with-cancer

SVM detailed analysis for predicting gender:
https://www.kaggle.com/nirajvermafcb/support-vector-machine-detail-analysis

## Setting up CNTK on Windows

Spin up a DSVM windows server 2012 VM. Remote Desktop in using your username and password credentials you created. 

Remember to `conda install scikit-image` then go download the wheel for opencv [here](http://www.lfd.uci.edu/~gohlke/pythonlibs/) and install using pip install. 

[Helpful link for installation FAQ](https://catinthemorning.wordpress.com/2017/02/12/install-cntk-on-windows/)

[Use your own data](https://docs.microsoft.com/en-us/cognitive-toolkit/Object-Detection-using-Fast-R-CNN#train-on-your-own-data)

Remember to run `activate py35` before running any scripts. 

## Setting up CNTK on Linux

Set up the Linux Data Science Virtual Machine from the Cortana Intelligence Gallery. **Update** JK found out that this is buggy so better to go to Azure portal > New > then search for dsvm linux and spin it up from the portal. Don't forget to agree to the programmatic agreement. 

Run `dsvm-more-info` for more info on the ML tools in the VM.

Activate the python 3.5 environment with `source /anaconda/bin/activate py35`

Go get CNTK 2.0, [instructions](https://docs.microsoft.com/en-us/cognitive-toolkit/Setup-Linux-Python)

[set up VM](https://docs.microsoft.com/en-us/azure/machine-learning/machine-learning-data-science-linux-dsvm-intro)

`git clone https://github.com/Azure/ObjectDetectionUsingCntk.git`

Pip install the following (in sudo): 

- opencv-python
- scikit-learn
- Pillow
- future
- dlib - this takes ages
- EasyDict

Make sure you use `sudo /anaconda/envs/py35/bin/pip install <package> # for Python 3.5 environment` so that it installs in the right environment

