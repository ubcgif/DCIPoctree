.. _example_sensitivity:

Sensitivity Weights
===================

Here, the code **dcsensitivity.exe** and the input file **sens.inp** (:ref:`see format <dcip_input_weights>`) are used to create a sensitivity weights file. This counteracts the dc inversion's natural tendancy to incorrectly place anomalous structures near the electrodes. Files relevant to this part of the example are in the sub-folder *sensitivity_weights*. Before running this example, you may want to do the following:

	- `Download and open the zip folder containing the entire DCIP octree example <https://github.com/ubcgif/DCIPoctree/raw/master/assets/dcipoctree_example.zip>`__ (if not done already)
	- :ref:`Learn how to run code from command line <dcip_sensitivity_weights>`
	- :ref:`Learn the format of the input file <dcip_input_sens>`

To generate the sensitivity weights, the following input file was used:

.. figure:: ../inputfiles/images/create_sens_input.png
     :align: center
     :width: 700


