.. _dcip_octree:

Create OcTree Mesh
==================

:ref:`OcTree meshes<octreeFile>` used in the DCIP octree code are created using the program **create_octree_mesh_dcip.exe**. Parameters necessary for defining the OcTree mesh are set in the :ref:`input file<dcip_input_octree>`; referred to here as **octree_mesh.inp**.

To generate the OcTree mesh, open a command window. Type the path to the code **create_octree_mesh_dcip.exe**, followed by a space, followed by the path to the input file.

.. figure:: images/run_create_mesh.png
     :align: center
     :width: 700



.. _dcip_octree_output:


The program **create_octree_mesh_dcip.exe** creates 6 output files:

    - **data_Z.txt:** A survey/observations file with XYZ locations defined by the OcTree mesh. That is:

    	- If the :ref:`LOC_XY flag<dcip_input_octreeln5>` is used in the input file, *data_Z.txt* will the define X,Y and Z positions for electrodes
    	- If the input survey file is an observations file, *data_Z.txt* will preserve the data columns
    	- Any surface electrodes will be shifted to the location of the discretized topography
    	- Any borehole electrodes will stay at the same location

    - **3D_mesh.txt:** the underlying regular tensor mesh. This mesh is comprised of the smallest cell size and is very large (>> 1M cells). As a result, it is unwise to plot this mesh.

    - **3D_core_mesh.txt:** A 3D regular tensor mesh defining the core region. 

    - **octree_mesh.txt:** :ref:`OcTree mesh<octreeFile>` used in the forward modeling and inversion codes

    - **active_cells_topo.txt:** :ref:`active cells model<modelFile>` on the OcTree mesh. Cells are active if assigned a value of 1 and inactive if assigned a value of 0. This file is not created if the *NO_TOPO* flag is used.

    - **create_octree_mesh_e3d.log:** log file













