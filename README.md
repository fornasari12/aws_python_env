[![Python 3.8](https://github.com/fornasari12/aws_python_env/actions/workflows/main.yml/badge.svg)](https://github.com/fornasari12/aws_python_env/actions/workflows/main.yml)  [![Python 3.6](https://github.com/fornasari12/python_scaffold/actions/workflows/azure.yml/badge.svg)](https://github.com/fornasari12/python_scaffold/actions/workflows/azure.yml)


# Python Project Scaffold

[Link to Course repository](https://github.com/noahgift/scaffold)

<img width="1530" alt="Screen Shot 2021-05-26 at 08 52 13" src="https://user-images.githubusercontent.com/57304126/119655195-b0799400-bdff-11eb-8a4a-4d9a9935e156.png">

1. Connect to a GitHub repository with SSH keys and clone repository

```shell
# Press Enter to store the keys in home directory
echo "ssh"ssh-keygen -t rsa

# Print the key store in the directory.
cat /home/ec2-user/.ssh/id_rsa.pub

git clone git@github.com:fornasari12/aws_python_env.git
```

2. Create required files.

```shell
touch Makefile
touch hello.py
touch test_hello.py
touch requirements.txt
```

3. Create invisible Python virtual enviroment.

```shell
# create the venv with the same name of the repo
git remote -v

# create virtual env
python3 -m venv ~/.aws_python_env

# activate
source ~/.aws_python_env/bin/activate  
```

4. Fill Makefile

```
install:
	pip install --upgrade pip &&\
		pip install -r requirements.txt

format:
	black *.py

lint:
	pylint --disable=R,C hello.py

test:
	python -m pytest -vv --cov=hello test_hello.py
```

4. Fill requirements

```
pylint
pytest
click
black
pytest-cov
```

5. Run

```
make lint
make format
make test

