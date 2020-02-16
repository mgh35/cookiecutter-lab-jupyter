# Cookiecutter - Lab using Jupyter

Template for creating labs with a Jupyter Lab interface.

Inspired by: https://florianwilhelm.info/2018/11/working_efficiently_with_jupyter_lab/

The idea is that to:
 
1) Create and run a Jupyter Lab instance under a virtual env
2) Create an empty package you can populate which will be accessible in that Jupyer Lab instance



### Create a new lab

```bash
pip install cookiecutter
cookiecutter git@github.com:mgh35/cookiecutter-lab-jupyter.git
```


### Run your lab

To run, go into the new repo you've created and run:

```
./run.sh
```


### Packages available in the Jupyter Lab environment

Packages available in the Jupyter environment are set in `requirements.txt`. 

To update, add the dependency there and recreate the lock file with 

```
./lock.sh
```

You will need to rerun the lab to pick up the changes.



### Local package

Your local package will be available in Jupyter Lab. You can import with:

```
import {{cookiecutter.project_slug}}
```

It's run in `develop` mode, so will pick up changes live. To pick up the updates in Jupyter Lab live, include:

```
%load_ext autoreload
%autoreload 2
```

### Local package dependencies

Dependencies for the local package are set in the `install_requires` section of `setup.py`. 

You will need to rerun the lab to pick up the changes.
