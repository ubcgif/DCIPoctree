.. _elements:

.. warning:: This manual contains the documentation for DCIP octree package releases **beginning on 2020-05-08**. This version of the package is compatible with GIFtools v2.31 and later. If using an earlier version of GIFtools, please see the `2014-10 release manual <https://dcipoctree.readthedocs.io/en/2014-10/>`__ .

Elements of the DCIP octree package
===================================

This section provides a brief description of each program in the DCIP octree package. In addition, we describe the file formats for all input and supporting files used by the coding library.

Executables
-----------

The main executable programs within the DCIP octree program library are:

    - **create_octree_mesh_dcip:** creates an OcTree mesh based on the survey geometry
    - **dcipoctree_fwd:** used to forward model both DC and IP data
    - **dcsensitivity:** approximates the sensitivities for the DC or IP problem
    - **sens2weights:** creates sensitivity weights from sensitivities
    - **dcoctree_inv:** inverts DC data to recover a conductivity model
    - **ipoctree_inv:** inverts IP data to recover a chargeabitiliy model

The following Octree utility programs may also be helpful:

    - **blk3cellOct:** creates conductivity models on an OcTree mesh
    - **create_weight_file:** creates the weighting on each cell in the model
    - **interface_weights:** creates weights on the faces of cells


Main Input Files
----------------

Here, we describe the main input files for executables contained with the DCIP octree coding package.

.. tOcTree::
    :maxdepth: 1

    Create OcTree mesh <inputfiles/createOcTree>
    Create OcTree model <inputfiles/createModel>
    Forward modeling <inputfiles/forward>
    Sensitivity weights <inputfiles/sensFile>
    Interface weights <inputfiles/weightsFile>
    DC Inversion <inputfiles/dcinversion>
    IP Inversion <inputfiles/ipinversion>


Supporting Files
----------------

Here, we describe the formats of supporting files used to run DCIP octree executable files. The input files for each executable program are described in the :ref:`running the programs<running>` section.

.. toctree::
    :maxdepth: 1

    Survey File <files/surveyFile>
    Predicted Data File <files/preFile>
    Observations File <files/obsFile>
    Topography File <files/topoFile>
    Active Model File <files/activemodel>
    OcTree Mesh File <files/octree_mesh>
    Model File <files/model>
    Model and Face Weights Files <files/weightsFile>
    Bounds File <files/bounds>
