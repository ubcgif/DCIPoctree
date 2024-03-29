.. _dcip_weights:

Create Additional Cell, Sensitivity and Face Weights
====================================================

The creation of specific cell and face weights is not required to run the inversion. However, the user may want to weight the relative contributions of cells and/or gradients in certain regions towards the model objective function; see :ref:`theory: inversion <theory_inv>`. The user may also want to apply weights that reduce the impact of near surface artifacts due to receivers.


.. _dcip_sensitivity_weights:

Generating Sensitivity Weights File
-----------------------------------

Sensitivity weights are used to counteract the mislocation of anomalous bodies due to the sensitivity of certain cells to the data. Sensitivity weights can be applied in the smallness and smoothness term of the model objective function; see :ref:`theory: inversion <theory_inv>`. Generating sensitivity weights is a 2-step process.

Step 1: Computing Sensitivities
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Before creating the sensitivity weights, you must first approximate the sensitivities. To compute approximated sensitivities on an Octree mesh, open a command window. In order, enter the path to **dcsensitivity.exe**, followed by the path to the :ref:`input file<dcip_input_sens>`; denoted here as **sens.inp**: 

.. figure:: images/run_sensitivity.png
    :align: center
    :width: 700


**Output Files:**

The program **dcsensitivity.exe** creates the following output files:

    - **sensitivities.txt:** the root mean squared sensitivities computed according to equation :eq:`sensitivities_rms`

    - **dcsensitivity.log:** a log file


Step 2: Sensitivity Weights
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Using the approximated sensitivities from step 1, we would like to create a sensitivity weights file. In the command window you have opened, or in a new one, enter the path to **sens2weights.exe**, followed by the path to the :ref:`input file<dcip_input_sens>`; denoted here as **sens2weights.inp**:


.. figure:: images/run_sens2weights.png
    :align: center
    :width: 700


**Output Files:**

The program **sens2weights.exe** creates the following output files:

    - **sensitivity weights** A sensitivity weights file with a user-specified name

    - **sens2weights.log:** a log file



Generating Model Weights File
-----------------------------

Model weights are applied in the smallness and smoothness terms of the model objective function; see :ref:`theory: inversion <theory_inv>`. To generate a model weights file, use the same workflow described on the :ref:`create model <dcip_model>` page. When creating a model weight file, consider the following:

     - All cells **must** be assigned a weight values larger than 0! This is to ensure the problem is sufficiently well-conditioned.
     - Model weight values should be set relative to a value of 1. This is to ensure the relative emphasis on model weights and surface weights is preserved.
     - Large model weights (:math:`w \gg 1` ) are used for cells that we want to match the reference model. Small model weights (:math:`w \ll 1` ) are used for cells to reduce the impact of the reference model on the cells. 


.. _dcip_interface_weights:

Generating Interface Weights File
---------------------------------

Interface weights are used to preserve the gradients or edges within certain regions of the reference model. They are also used to reduce near-surface artifacts which result from the sensitivity to the receiver locations. Interface weights are applied within the gradient terms of the model objective function; see :ref:`theory: inversion <theory_inv>`. When creating interface weights, consider the following:

     - All interface weights **must** be larger than 0! This is to ensure the problem is sufficiently well-conditioned.
     - Interface weight values should be set relative to a value of 1. This is to ensure the relative emphasis on model weights and surface weights is preserved.
     - Large interface weights (:math:`w \gg 1` ) preserve gradients within reference model. Small interface weights (:math:`w \ll 1` ) results in smoother gradients within the recovered model. 


To generate interface weights on an Octree mesh, open a command window. In order, enter the path to **interface_weights.exe**, followed by the path to the :ref:`input file<dcip_input_weights>`; denoted here as **interface_weights.inp**: 

.. figure:: images/run_interface_weights.png
    :align: center
    :width: 700


Output File
^^^^^^^^^^^

The executable outputs an interface_weights file with the specified output name. This file stores the interface weights in X, Y and Z in a single column; as the number of faces in the X, Y and Z direction are likely different.






