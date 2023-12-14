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

<arborize.builders._neuron.NeuronModel object at 0x7f13a7f30df0>
numprocs=1
[LAPTOP-JF6T3PSU:26393] *** Process received signal ***
[LAPTOP-JF6T3PSU:26393] Signal: Segmentation fault (11)
[LAPTOP-JF6T3PSU:26393] Signal code: Address not mapped (1)
[LAPTOP-JF6T3PSU:26393] Failing at address: 0x50
[LAPTOP-JF6T3PSU:26393] [ 0] /lib/x86_64-linux-gnu/libpthread.so.0(+0x14420)[0x7f13ff56f420]
[LAPTOP-JF6T3PSU:26393] [ 1] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrniv.so(_ZN15BBSDirectServer12context_waitEv+0x0)[0x7f13ab91bdd0]
[LAPTOP-JF6T3PSU:26393] [ 2] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrnmpi_ompi.so(f_nrnmpi_mindelay+0x1c)[0x7f13ab65119c]
[LAPTOP-JF6T3PSU:26393] [ 3] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrniv.so(+0x291870)[0x7f13ab93d870]
[LAPTOP-JF6T3PSU:26393] [ 4] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrniv.so(_ZN3BBS15netpar_mindelayEd+0x42)[0x7f13ab9414b2]
[LAPTOP-JF6T3PSU:26393] [ 5] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrniv.so(hoc_call_ob_proc+0x1b7)[0x7f13ab9ac757]
[LAPTOP-JF6T3PSU:26393] [ 6] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrniv.so(_Z20hoc_object_componentv+0x383)[0x7f13ab9ad3a3]
[LAPTOP-JF6T3PSU:26393] [ 7] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrnpython3.so(+0x11e21)[0x7f13ab66de21]
[LAPTOP-JF6T3PSU:26393] [ 8] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrnpython3.so(+0x18a52)[0x7f13ab674a52]
[LAPTOP-JF6T3PSU:26393] [ 9] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrniv.so(_ZN10OcJumpImpl7fpycallEPFPvS0_S0_ES0_S0_+0x42)[0x7f13ab960b72]
[LAPTOP-JF6T3PSU:26393] [10] /home/robin/.pyenv/versions/beta-models/lib/python3.9/site-packages/neuron/.data/lib/libnrnpython3.so(+0x12d9c)[0x7f13ab66ed9c]
[LAPTOP-JF6T3PSU:26393] [11] /home/robin/.pyenv/versions/beta-models/bin/python(_PyObject_MakeTpCall+0x94)[0x5567aa402e64]
[LAPTOP-JF6T3PSU:26393] [12] /home/robin/.pyenv/versions/beta-models/bin/python(_PyEval_EvalFrameDefault+0x7fe8)[0x5567aa3f3d08]
[LAPTOP-JF6T3PSU:26393] [13] /home/robin/.pyenv/versions/beta-models/bin/python(+0x1277ba)[0x5567aa4b67ba]
[LAPTOP-JF6T3PSU:26393] [14] /home/robin/.pyenv/versions/beta-models/bin/python(_PyFunction_Vectorcall+0x97)[0x5567aa403e37]
[LAPTOP-JF6T3PSU:26393] [15] /home/robin/.pyenv/versions/beta-models/bin/python(+0x210f88)[0x5567aa59ff88]
[LAPTOP-JF6T3PSU:26393] [16] /home/robin/.pyenv/versions/beta-models/bin/python(_PyEval_EvalFrameDefault+0x723e)[0x5567aa3f2f5e]
[LAPTOP-JF6T3PSU:26393] [17] /home/robin/.pyenv/versions/beta-models/bin/python(+0x1277ba)[0x5567aa4b67ba]
[LAPTOP-JF6T3PSU:26393] [18] /home/robin/.pyenv/versions/beta-models/bin/python(_PyFunction_Vectorcall+0x97)[0x5567aa403e37]
[LAPTOP-JF6T3PSU:26393] [19] /home/robin/.pyenv/versions/beta-models/bin/python(+0x210f88)[0x5567aa59ff88]
[LAPTOP-JF6T3PSU:26393] [20] /home/robin/.pyenv/versions/beta-models/bin/python(_PyEval_EvalFrameDefault+0x6068)[0x5567aa3f1d88]
[LAPTOP-JF6T3PSU:26393] [21] /home/robin/.pyenv/versions/beta-models/bin/python(+0x1277ba)[0x5567aa4b67ba]
[LAPTOP-JF6T3PSU:26393] [22] /home/robin/.pyenv/versions/beta-models/bin/python(_PyFunction_Vectorcall+0x97)[0x5567aa403e37]
[LAPTOP-JF6T3PSU:26393] [23] /home/robin/.pyenv/versions/beta-models/bin/python(+0x210f88)[0x5567aa59ff88]
[LAPTOP-JF6T3PSU:26393] [24] /home/robin/.pyenv/versions/beta-models/bin/python(_PyEval_EvalFrameDefault+0x723e)[0x5567aa3f2f5e]
[LAPTOP-JF6T3PSU:26393] [25] /home/robin/.pyenv/versions/beta-models/bin/python(+0x1277ba)[0x5567aa4b67ba]
[LAPTOP-JF6T3PSU:26393] [26] /home/robin/.pyenv/versions/beta-models/bin/python(PyEval_EvalCode+0x3a)[0x5567aa4b6aea]
[LAPTOP-JF6T3PSU:26393] [27] /home/robin/.pyenv/versions/beta-models/bin/python(+0x1688b7)[0x5567aa4f78b7]
[LAPTOP-JF6T3PSU:26393] [28] /home/robin/.pyenv/versions/beta-models/bin/python(+0x16a2a8)[0x5567aa4f92a8]
[LAPTOP-JF6T3PSU:26393] [29] /home/robin/.pyenv/versions/beta-models/bin/python(PyRun_InteractiveLoopFlags+0x96)[0x5567aa4f9576]
[LAPTOP-JF6T3PSU:26393] *** End of error message ***
Segmentation fault
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

numprocs=1
<arborize.builders._neuron.NeuronModel object at 0x7f209751ab50>
```
