How do i create conda environments?

```bash
conda create -n my-default
conda install -n my-default pip
source activate my-default
pip install numpy
```

To install packages while creating:

```bash

```

To look at the dependencies:

```bash
conda list --explicit
```

To create a spec file:

```bash
conda list --explicit > spec-file.txt
conda env export > environment.yml
```

To list all conda environments:

```bash
conda info --envs
```

To see if a specific package is installed in an environment

```bash
conda list -n myenv scipy
``` 

To save environment variables:

```bash
cd /home/jsmith/anaconda3/envs/analytics
mkdir -p ./etc/conda/activate.d
mkdir -p ./etc/conda/deactivate.d
touch ./etc/conda/activate.d/env_vars.sh
touch ./etc/conda/deactivate.d/env_vars.sh
```

Edit `.\etc\conda\activate.d\env_vars.sh` as follows:

```bash
#!/bin/sh

export MY_KEY='secret-key-value'
export MY_FILE=/path/to/my/file/
```

Edit `.\etc\conda\deactivate.d\env_vars.sh` as follows:
```
#!/bin/sh

unset MY_KEY
unset MY_FILE
```
To remove an environment:

```bash
conda remove --name myenv --all
conda env remove --name myenv
```

IPython is not virtualenv-aware and that the most logical solution to this is to 
install ipython in each virtualenv seperately using

```bash
pip install ipython
pip install jupyter
```

If the system-wide copy of IPython is called from within a virtualenv using 
$> ipython before IPython is installed under this virtualenv, subsequent 
$> ipython commands will continue to bring up the system-wide ipython copy.

On the other hand, if ipython is not called prior to installing it under a 
virtualenv $> ipython will bring up the newly installed copy.

One way of always being sure that the ipython instance always belongs to the 
virtualenv's python version is to create an alias as below and use it to invoke ipython.

```bash
alias ipy="python -c 'import IPython; IPython.terminal.ipapp.launch_new_instance()'"
ipy notebook
```