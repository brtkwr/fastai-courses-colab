# Usage

Install prerequisites
```
apt-get install python3
apt-get install python3-dev
apt-get install virtualenvpip 
```
Then

```
git clone git@github.com:strange-labs-uk/fast.ai
cd fast.ai
virtualenv -p python3 ./Fast.ai-virtualenv
source ./Fast.ai-virtualenv/bin/activate
pip install -r requirements.txt
jupyter notebook
```