.. _dcip_surface_electrodes:

Project Electrodes to Surface
=============================

The program **surface_electrodes.exe** is used to project electrodes to the discrete surface topography. This is needed when 1) you have a *surface formatted* survey/observations file, or 2) the survey/observations file has the true elevations of the electrodes and must be projected to the discretize surface topography. Parameters necessary for defining the OcTree mesh are set in the :ref:`input file<dcip_input_surface_electrodes>`; referred to here as **octree_mesh.inp**.

To generate a survey/observations file with electrodes on the discrete surface topography, open a command window. Next, type the path to the code **surface_electrodes.exe**, followed by a space, followed by the path to the input file.

.. figure:: images/run_surface_electrodes.PNG
     :align: center
     :width: 700



