# Mantaflow #

Mantaflow is an open-source framework targeted at fluid simulation research in Computer Graphics.
Its parallelized C++ solver core, python scene definition interface and plugin system allow for quickly prototyping and testing new algorithms. 

In addition, it provides a toolbox of examples for deep learning experiments with fluids. E.g., it contains examples
how to build convolutional neural network setups in conjunction with the [tensorflow framework](https://www.tensorflow.org).

For more information on how to install, run and code with Mantaflow, please head over to our home page at
[http://mantaflow.com](http://mantaflow.com)

## How to write a python scene file

### Set solver params

How much of resolution the simulation need to operate?

### Prepare grids

Prepare grids for:

- flags?
- velocity()
- density()
- pressure()

### Set noise field

### Set source

This is a source, which is used for inflow smog.

### GUI

Do we need to open GUI? If so, show the GUI.

### Start main loop

```python
for t in range(250 [Total steps] ):
    # print out which frame it is 
    mantaMsg('\nFrame %i' % (s.frame))
    
    If there is something getting in our solver, then put it like densityInflow()
    
    advectSemiLagrange(flags, vel, grid, order)
    advectSemiLagrange(flags, vel, grid, order, strength)
    
    setWallBcs(flags, vel)
    addBuoyancy(density, vel, gravity, flags)
    SolvePressure(flags, vel, pressure)
    s.step()
```

