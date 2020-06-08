.. _dcip_input_sens:

Sensitivity Weights
===================

The parameters used to create sensitivity weights are defined in the input file. The lines within the input file are as follows:


.. tabularcolumns:: |L|C|C|

+--------+----------------------------------------------------+---------------------------------------------------------+
| Line # | Parameter                                          | Description                                             |
+========+====================================================+=========================================================+
| 1      | :ref:`OcTree Mesh<dcip_sens_ln1>`                  | path to octree mesh                                     |
+--------+----------------------------------------------------+---------------------------------------------------------+
| 2      | :ref:`Survey File<dcip_sens_ln2>`                  | survey file (locations of observations)                 |
+--------+----------------------------------------------------+---------------------------------------------------------+
| 3      | :ref:`Conductivity Model<dcip_sens_ln3>`           | path to conductivity model                              |
+--------+----------------------------------------------------+---------------------------------------------------------+
| 4      | :ref:`Active Cells<dcip_sens_ln4>`                 | path to active cells model                              |
+--------+----------------------------------------------------+---------------------------------------------------------+
| 5      | :ref:`# Samples <dcip_sens_ln5>`                   | number of iterations used to approximate sensitivities  |
+--------+----------------------------------------------------+---------------------------------------------------------+
| 6      | :ref:`Method <dcip_sens_ln6>`                      | approximation method for sensitivity computation        |
+--------+----------------------------------------------------+---------------------------------------------------------+
| 7      | :ref:`Truncation value<dcip_sens_ln7>`             | val | (0 for no weights)                                |
+--------+----------------------------------------------------+---------------------------------------------------------+


.. figure:: images/create_sens_input.png
     :align: center
     :width: 700

     Example input file for creating interface senss (`Download <https://github.com/ubcgif/dcip/raw/dcip/assets/dcip_input/sens.inp>`__ ).


.. _dcip_input_senss_lines:

Line Descriptions
^^^^^^^^^^^^^^^^^

.. _dcip_sens_ln1:

    - **OcTree Mesh:** file path to the OcTree mesh file

.. _dcip_sens_ln2:

    - **Survey File:** This line defines the survey file. The general syntax is *LOC_XY|LOC_XYZ filepath*.

        - *LOC_XY|LOC_XYZ:* If the electrodes are all on the Earth's surface, use the flag *LOC_XY*. If the survey file contains any borehole measurements, use the flag *LOC_XYZ*.
        - *filepath:* This is the filepath to the survey/observations file. 

.. _dcip_sens_ln3:

    - **Conductivity Model:** On this line we specify the conductivity model for the sensitivity computation. On this line, there are 2 possible options:

        - Enter the path to a conductivity model
        - If a homogeneous conductivity value is being used, enter "VALUE" followed by a space and a numerical value; example "VALUE 0.01".

.. _dcip_sens_ln4:

    - **Active Topography Cells:** Here, the user can choose to specify the cells which lie below the surface topography. To do this, the user may supply the file path to an active cells model file or type "ALL_ACTIVE". The active cells model has values 1 for cells lying below the surface topography and values 0 for cells lying above.

.. _dcip_sens_ln5:

    - **# Samples:** This is the number of samples used to approximate the sensitivities. Somewhere between 5 and 20 samples are generally needed. A reasonable default value is 10. For more, see :ref:`theory section <theory_sensitivity_weights>` .

.. _dcip_sens_ln6:

    - **Method:** The method for approximating the sensitivity weights. The user enters a flag value of *1*, *2* or *3*:

        - (1) Hutchinson approach with :math:`v = \pm 1`
        - (2) Hutchinson approach with :math:`-1 < v < 1`
        - (3) Probing method


.. _dcip_sens_ln7:

    - **Truncation value:** If the difference between the largest and smallest sensitivity weights value spans too many orders of magnitude, it will negatively impact the stability of the inversion. The user will enter the minimum value for the sensitivity weights model. Note that the sensitivity weights model is normalized so that the largest value is 1. So for example, if a value of *0.001* is entered, the largest value in the sensitivity weights model will be 1, and all cells with normalized weights less than 0.001 will be set to 0.001. For more, see :ref:`theory section <theory_sensitivity_weights>` .


