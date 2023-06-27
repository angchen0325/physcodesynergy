## 001. Monthly meeting schedule (2023-06-23)

To fully exploit physics and coding synergy, we're going to have a monthly meeting schedule:
1. Approximately once a month, the specific meeting time will be confirmed three days in advance.
2. The focus of the meetings will be on programming as a tool to solve specific research-related problems: Programming is likened to a shovel, while research is the gold mine.
3. In the first six months, the meetings will primarily cover the fundamentals of physics as the gold mine, teaching participants to use tools like `python` as shovels. After six months, we will progress to using advanced shovels: `python` + `artificial intelligence (AI)`.

### 001.1 Terminals
To be novice friendly, here we digress a little to talk about the terminals on three different platforms. MacOS and Linux quite similar terminals, different from that of Windows. For Windows, we recommend `powershell` instead of `cmd` since it has a similar instruction set as MacOS/Linux. When using VScode, all those terminals can be integrated.

### 001.2 Python installation
Here we talk about how to install `python3` on Windows. 
It's easy to install `python3` from the [official website](https://www.python.org/downloads/). But the command in the terminal is initially "python". If you want to change it to "python3", you can follow these steps:
* Use the following command to find the installation path of python 3:
```python
import sys
sys.executable
```
* Once you have located the python 3 installation path, navigate to that directory.
* Rename the `python.exe` file to `python3.exe`, and the `pythonw.exe` file to `pythonw3.exe`.

After renaming, the `pip` or `pip3` command may encounter errors, and one potential solution is
```console
$ python3 -m pip install --upgrade --force-reinstall pip
```
### 001.3 Deployment of python virtual environment
We highly recommend you to have `venv` named `yourenv` (decided by you) available, since it's terse for you to manage those python packages. There are two methods to meet such needs: `conda` and `pip/pip3`.
#### 001.3.1 Using conda
We recommend [Anaconda](https://www.anaconda.com/products/distribution), using the free distribution installation. And then you can make a conda environment in the terminal:
```console
$ conda create -n yourenv python=3.x
```
Then you can find the Conda Env `yourenv` to run both `*.py` and `*.ipynb` files in VScode.
In terminal or integrated terminal, you can activate by
```console
$ conda activate yourenv
```
and deactivate by
```console
(yourenv) $ conda deactivate
```
But `conda` environments come with a set of pre-installed Python libraries, which can sometimes conflict with newly installed libraries. Thus we recommend the following method.

#### 001.3.2 Using pip/pip3
Using `pip/pip3` to make a virtual environment with:
```console
$ python3 -m venv yourenv
```
In terminal or integrated terminal on Windows, you can activate by
```console
$ .\[path of yourenv]\yourenv\Scripts\activate
```

If can't, run the terminal as an administrator
```console
$ set-ExecutionPolicy RemoteSigned
```
then `Enter`, and chose `Y`. 
And you can deactivate the `venv` by
```console
(yourenv) $ deactivate
```

#### 001.3.3 Third-party libraries
When first deploying a `venv`, there're two libraries, and you can look them up with
```console
(yourenv) $ pip3 list
```
and you can see
```console
Package     Version
----------  -------
pip         22.0.4
setuptools  58.1.0
```
Here `pip` and `setuptools` are built-in with `yourenv`. 
If you want to install other third-party libraries like `numpy`, you can install them with
```console
(yourenv) $ pip3 install numpy
```
or
```console
(yourenv) $ pip3 install numpy -i https://pypi.tuna.tsinghua.edu.cn/simple/
```
The option `-i` is used to specify the index source from where the package will be installed. Here we can use the index source from [tuna](https://mirrors.tuna.tsinghua.edu.cn), Tsinghua University open source software mirror. By default, `pip3` downloads packages from the [Python Package Index](https://pypi.org) (PyPI). Then you can see
```console
Package     Version
----------  -------
numpy       1.25.0
pip         22.0.4
setuptools  58.1.0
```
To export the dependencies used in `yourenv` to a `requirements.txt` file, you can use the following command:
```console
pip3 freeze > requirements.txt
```
If you want to transfer `yourenv` to your code collaborators, just send them the `requirements.txt` file and tell them to use the command:
```console
pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple/
```

#### 001.3.4 Select python interpreter
We recommend [VScode](https://code.visualstudio.com) as our coding editor. We usually deal with two kinds of python files: `.py` file and `.ipynb` file. 

When opening a `.py` file, you can
* Enter `shift`+`control`+`P` to open `Command Palette` 
* Click `Python: Select Interpreter` and then `+ Enter interpreter path...`
* Imput `[python3 path of yourenv]`

Then you can enter the button &#x25B6; and run the `.py` file.
After doing so, you can open a `.ipynb` file, and
* Click `Select Kernel` 
* Select `Select Another Kernel...` and `Python Environments...`
* Choose `yourenv`

Here we can test `print_hello.py` and `print_hello.ipynb`.