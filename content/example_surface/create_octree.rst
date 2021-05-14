.. _example_octree_surface:

Create OcTree Mesh
==================

Here, the code **create_octree_mesh_dcip.exe** and the input file **octree_mesh.inp** (:ref:`see format <dcip_input_octree>`) are used to create an OcTree mesh based on the set of electrode locations and surface topography. Files relevant to this part of the example are in the sub-folder *octree_mesh*.

Before running this example, you may want to do the following:

	- `Download and open the zip folder containing the entire DCIP octree example <https://github.com/ubcgif/DCIPoctree/raw/master/assets/dcipoctree_example_surface.zip>`__ (if not done already)
	- :ref:`Learn how to run code from command line <dcip_octree>`
	- :ref:`Learn the format of the input file <dcip_input_octree>`

For our example, the :ref:`survey file <surveyFile>` uses the **surface format** , which means there are no elevations provided for the electrode locations. In this case, we assume all electrodes live on the discrete surface topography that is defined when creating the mesh.

To generate the OcTree mesh, the following input file was used:

.. figure:: images/octree_input.png
     :align: center
     :width: 700


Below we plot the resulting OcTree mesh and original topography (left) as well as the active cells model (right). The active cells model defines the discrete surface topography by assigning a 1 to cells that are in the ground and a 0 to cells that are in the air.

.. figure:: images/octree_mesh.png
     :align: center
     :width: 700



