# Usage

## Prerequisites:

The [fast.ai](https://fast.ai) python package requires Python 3.6 or higher.

On Ubuntu:

```
sudo add-apt-repository ppa:jonathonf/python-3.6
sudo apt update
sudo apt install python3.6
```

On a Mac:

Install the latest [HomeBrew](https://brew.sh) by running the following command:

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Then,
```
brew install python3
```

If you have Anaconda installed, you may need to removing it from your $PATH by
commenting it out from your `~/.profile` or `~/.bash_profile`.

## Setup:

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
