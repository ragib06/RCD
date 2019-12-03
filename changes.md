# Changes made to original RCD source

## Dependency changes

- ~~Python 3.3~~ -> Python 3.6
- NetworkX 1.7
- Numpy 1.7
- Mock 1.0.1
- ~~rpy2 2.3~~ -> rpy2 3.0.0

## Code changes

In order to make the code working, a tiny change was needed particularly because of using a different version **rpy2** package compared to the one the authors used initially.

- In line 60, 61 and 63 ```causality/citest/CITest.py``` a function called ```baseenv()``` was used. We changed it to ```globalenv()``` like this:

    ```robjects.globalenv['treatment'] = robjects.FloatVector(relVar1Data)```

- The import satements were using absolute paths to modules which is a bit problematic. We changed them to relative paths. For example in the same ```CITest.py``` line 2, you'd see something like this:

    ```from ..model.RelationalDependency import RelationalVariable```

    Note that, this is not mandatory. The code will run fine without changing it. But if you want to use any of the modules in your custom code, its better to change this way.