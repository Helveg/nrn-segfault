Segfault reproducer
===================

Begin by setting up a new virtualenv, and install the requirements:

```
python -m virtualenv segfaultenv
./segfaultenv/bin/activate
pip install -r requirements.txt
```

Run the code for the segfault:

```
python segfault.py
```

Install `mpi4py` to fix the problem:

```
sudo apt-get update
sudo apt-get install openmpi-bin libopenmpi-dev
pip install mpi4py
```

Run again without issues:

```
python segfault.py
```
