### Conda-Jupyter-Docker

- How to build your own docker container from an anaconda docker image?
- How to create conda environment from a .yml file in the docker container?
- How to install the conda environment to the kernel list in jupyter notebook?
- How to launch jupyter notebook from the container?

#### Access the Jupyter notebook from your remote machine over SSH
```
$ ssh -L 2222:localhost:2222 <REMOTE_USER>@<REMOTE_HOST>
```

#### Go to your docker path
```
$ /Path/to/working/directory/docker 
```

#### Build docker container
```
$ docker build --no-cache -t deep_learning_docker .
```

#### Run docker container
```
$ docker run -it --rm --gpus all -p 2222:8888 -v /PATH/TO/WORKING/DIRECTORY/:/PATH/TO/WORKING/DIRECTORY/ deep_learning_docker
```

#### Activate conda environment
```
$ source activate env_name
```

#### After executing the above command we will be in the environment
```
(env_name) root@############:/Path/to/working/directory/#
```
#### Add your environment to Jupyter Notebook
```
$ python -m ipykernel install --user --name=env_name
```

#### Launch Jupyter notebook with default port from docker container
```
$ jupyter notebook --ip=0.0.0.0 --port=8888 --no-browser --allow-root
```

#### Enter the URL in your local browser 
Open a browser from your local machine and navigate to `http://localhost:2222/tree` and enter your token specified in your terminal.









