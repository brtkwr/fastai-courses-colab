# README.md

In this repo, we aim to replicate the notebooks available in fast.ai
[repository](https://github.com/fastai/fastai/tree/master/courses) but
in such a way that they are compatible with [Google's
Colab](https://research.google.com/) notebook environment
that has a free to use GPU backend (which you will need to enable via
Runtime -> Change runtime type). The notebooks are usually self
contained, i.e. it will install all the required packages and download
the relevant datasets using inline shell scripts since the kernels get
destroyed after 12 hours of use (I am hoping that they will eventually
allow storage and retrieval of data from Google Drive, which is only an
option for notebooks at the moment). As a result, the instructions below
are not relevant for Colab.

# Setting up fast.ai environment locally

NOTE: Only go ahead with this route if you have a decent nvidia GPU
(compute capability 3+) as anything lower does not support CUDNN and you
don't want to do deep learning on a CPU (your iteration cycle will
suffer).

The [fast.ai](https://fast.ai) python package requires Python 3.6 or
higher.

On Ubuntu:

```
sudo add-apt-repository ppa:jonathonf/python-3.6
sudo apt update
sudo apt install python3.6
```

On a Mac:

Install the latest [HomeBrew](https://brew.sh) by running the following
command:

```
/usr/bin/ruby -e "$(curl -fsSL
https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Then,
```
brew install python3
```

If you have Anaconda installed, you may need to removing it from your
`$PATH` bycommenting it out from your `~/.profile` or `~/.bash_profile`.

# Setup:

```
git clone git@github.com:strange-labs-uk/fast.ai
cd fast.ai
ENV=~/Envs/ML-Python3
mkdir -p $ENV
virtualenv -p python3 $ENV
echo "#! /bin/bash" > env.sh
echo ". $ENV/bin/activate" >> env.sh
. env.sh
pip install -r requirements.txt
jupyter notebook
```

# Dataset

Run the following script to download data which will automatically
download and unpack images of dogs and cats to `~/Datasets/dogscats`.

```
./get_dataset.sh
```
