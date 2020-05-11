.. _dcip_model:

Create Model
============

:ref:`Models<modelFile>` (conductivity) used within the this programming package are generated using **blk3cellOct.exe**. The model output by the executable is comprised of a set of overlapping rectangular blocks whose locations, dimensions and values are specified within the :ref:`input file<dcip_input_model>`; denoted here as **blk3cellOct.inp**.

.. note:: This workflow can also be used to create a model :ref:`weights file<weightsFile>`.


To generate the model on the octree mesh, open a command window. Enter the path to **blk3cellOct.exe**, followed by the path to the :ref:`input file<dcip_input_model>`; denoted here as **blk3cellOct.inp**. 

.. figure:: images/run_blk3cellOct.png
     :align: center
     :width: 500


**blk3cellOct.exe** outputs a :ref:`model<modelFile>` which contains a single value for each cell in the octree mesh.





