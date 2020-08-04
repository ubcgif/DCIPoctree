.. _example_weights:

Interface Weights
=================

.. note:: Depending on the application, this may or may not improve the final model.


Here, the utility code **interface_weights.exe** and the input file **interface_weights.inp** (:ref:`see format <dcip_input_weights>`) are used to create an surface interface weights. This limits negative effects due to the sensitivity of near-surface cells to surface electrodes by smoothing the near surface horizontally. Files relevant to this part of the example are in the sub-folder *interface_weights*. Before running this example, you may want to do the following:

	- `Download and open the zip folder containing the entire DCIP octree example <https://github.com/ubcgif/DCIPoctree/raw/master/assets/dcipoctree_example.zip>`__ (if not done already)
	- :ref:`Learn how to run code from command line <dcip_interface_weights>`
	- :ref:`Learn the format of the input file <dcip_input_face_weights>`

To generate the interface weights, the following input file was used:

.. figure:: ../inputfiles/images/interface_weights_input.png
     :align: center
     :width: 700




