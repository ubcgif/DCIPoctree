.. _elements:

.. important:: The 2014-10 release is compatible with GIFtools v2.30 and earlier. This version of the DCIPoctree package will not be maintained. For documentation of the latest version, see `latest DCIP octree manual <https://dcipoctree.readthedocs.io/en/latest/>`__ .

Elements of the program DCIPoctree (2014-10 release)
====================================================

The DCIPoctree library consists of three core programs and nine utilities.

Core Programs:

- ``DCIPoctreeFwd``: Forward model conductivity/chargeability models to calculate data

- ``DCoctreeInv``: Invert 3D DC data to develop a conductivity model

- ``IPoctreeInv``: Invert 3D IP data to develop a chargeablility model

Utilities:

- ``create_octree_mesh``: Create an octree mesh file from electrode locations and optionally topography

- ``3DModel2Octree``: Convert from a 3D UBC-GIF mesh/model to an octree mesh/model

- ``octreeTo3D``: Convert from an octree mesh/model to a standard 3D UBC-GIF mesh/model

- ``refine_octree``: Make an octree mesh finer based on the values of the input model

- ``remesh_octree_model``: Convert a model from one octree mesh to another

- ``surface_electrodes``: Place the electrodes on the topographic surface

- ``octree_cell_centre``: Read in an octree mesh, and output a 3-columns file of cell centres

- ``interface_weights``: Create a weight file for the octree cell interfaces

- ``create_weight_file``: Create an octree cell weighting file

Each of the above programs requires an input file (or files) in order to run. Before detailing the procedures for running each of the above programs, we first present information about these general input/output files.

.. _fileformats:

General files for DCIPoctree programs
-------------------------------------

**Input** files can have any user-defined name, while **output** files have restricted file names. Generall speaking, the filename extensions are not important. While the user can provide different file extensions for each file type (i.e. ``*.msh`` for mesh files, ``*.con`` for conductivity models), some users prefer to use the ``*.txt`` filename convention so that files are more easily read and edited in the Windows environment. There are ten general file types which are used by the different codes in DCIPoctree library:

.. toctree::
        :maxdepth: 1

        Octree mesh <files/octreemeshfile>
        Tensor mesh <files/tensormeshfile>
        Topography <files/topo>
        Observation/Location <files/dcipfile>
        Model <files/model>
        Weighting <files/weight>
        Bounds <files/bounds>
        Active model <files/activemodel>
