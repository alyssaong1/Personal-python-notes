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

## Setting up Tensorflow Object Detection API

Proto issues:
https://github.com/tensorflow/models/issues/1834#issuecomment-312476609



## Build your clone project 

### Setting up Tensorflow using Python 2.7 on a DSVM

Use the following:
https://www.tensorflow.org/install/install_linux#installing_with_anaconda
https://www.tensorflow.org/install/install_linux#the_url_of_the_tensorflow_python_package (select 2.7 CPU package)

Then run everything while inside the (tensorflow) environment

### Managing data

Truncating the dictionary: 
https://stackoverflow.com/questions/7971618/python-return-first-n-keyvalue-pairs-from-dict

## Tensorflow Seq2Seq translator project

Run this in the **root nmt folder**

python -m nmt.nmt \ --src=vi --tgt=en \ --vocab_prefix=nmt/iwslt15/vocab \ --train_prefix=nmt/iwslt15/train \ --dev_prefix=nmt/iwslt15/tst2012 \ --test_prefix=nmt/iwslt15/tst2013 \ --out_dir=nmt/iwslt15/nmt_model \ --num_train_steps=12000 \ --steps_per_stats=100 \ --num_layers=2 \ --num_units=128 \ --dropout=0.2 \ --metrics=bleu

If you want to retrain with different number of steps, make sure you delete contents in nmt_model first.

### Deploying to server
`source activate tensorflow`
`export FLASK_APP=predict.py`
Remember to use `flask run --host=0.0.0.0` to expose to a public server, see here: http://flask.pocoo.org/docs/0.12/quickstart/#quickstart

To list all ports running:
`lsof -i`

Make sure you put the index.html file into a templates folder - this is the default folder flash renders templates from.

## Azure ML installation
C:\Users\alon\AppData\Local\AmlInstaller\.datastore - make sure you delete everything in here when doing a reinstallation. Then run 
Installer.Windows.exe in the same AmlInstaller folder.

Merge issues:
Resolve the dsource and dsource.user file. Go back to the dsource in workbench. Click on "Prepare". Select the preparation package in the root folder. Then click on reference dataflow > edit > this file > click Ok

Add the following into .gitignore:
*.dprep.user
*.dsource.user

## Running the reddit RNN project
Downloading large gdrive files from ubuntu (see vladalive's comment) - https://gist.github.com/iamtekeste/3cdfd0366ebfd2c0d805

## Running cornell movie corpus RNN
https://github.com/suriyadeepan/practical_seq2seq

Create virtualenv and install tf 1.0 gpu 
Install nltk
Download the dataset from https://github.com/suriyadeepan/datasets/tree/master/seq2seq/cornell_movie_corpus/raw_data
Create the cornell corpus folder in the ckpt folder
https://www.tensorflow.org/install/install_windows#requirements_to_run_tensorflow_with_gpu_support

Creating a kernel for Jupyter using existing virtualenv:
http://anbasile.github.io/programming/2017/06/25/jupyter-venv/
