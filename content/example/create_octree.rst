.. _example_octree:

Create OcTree Mesh
==================

Here, the code **create_octree_mesh_dcip.exe** and the input file **octree_mesh.inp** (:ref:`see format <dcip_input_octree>`) are used to create an OcTree mesh based on the set of electrode locations and surface topography. Files relevant to this part of the example are in the sub-folder *octree_mesh*. To keep the example simple but generalizable, we will be using flat topography and defining the X, Y **and** Z positions of all electrodes. Before running this example, you may want to do the following:

	- `Download and open the zip folder containing the entire DCIP octree example <https://github.com/ubcgif/DCIPoctree/raw/master/assets/dcipoctree_example.zip>`__ (if not done already)
	- :ref:`Learn how to run code from command line <dcip_octree>`
	- :ref:`Learn the format of the input file <dcip_input_octree>`

To generate the OcTree mesh, the following input file was used:

.. figure:: ../inputfiles/images/create_octree_input.png
     :align: center
     :width: 700


The resulting OcTree mesh is shown below:

.. figure:: images/octree_mesh.png
     :align: center
     :width: 500



