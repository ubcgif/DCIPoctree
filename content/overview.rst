.. _overview:

.. warning:: This manual contains the documentation for DCIP octree package releases **beginning on 2020-05-08**. This version of the package is compatible with GIFtools v2.31 and later. If using an earlier version of GIFtools, please see the `2014-10 release manual <https://dcipoctree.readthedocs.io/en/2014-10/>`__ .

DCIPoctree package overview
===========================

New capabilities
----------------

DCIP3D for octree meshes (called DCIPoctree) is a program library for carrying out forward modelling and inversion of DC resistivity and induced polarization data over 3D structures. The forward and inverse modeling is done on a pre-defined base (underlaying) mesh, which can be selectively refined as per curvature amplitude, as dictated by property variations. 

Version 1.0 of the code is a newly developed algorithm, which has been developed for increased computational efficiency and higher level of modeling accuracy. The code is designed to replicate the capabilities available in the old UBC-GIF DCIP3D program library and its functionality, allows working with old data formats, whenever possible. In addition to the forward modeling and inversion routines, the program library includes numerous utility executables, designed to facilitate the transition from regular to octree meshes  and to support format exchange between the new and the old code versions.

In addition to the new approach in discretization, DCIPoctree has been released with implemented parallelization using OpenMP, optimized for usage on multi-core computers with hyperthreading functionality. For parallel usage on local networks and commodity clusters, DCIPoctree has been compiled with Message Pass Interface (MPI) using the `MUMPS direct solver <http://graal.ens-lyon.fr/MUMPS/>`__. 

The latest version (2020-05-08) uses pardiso and does not rely on MPI.

Among the newly implemented modifications to the beta version of the code, the most significant are the capability to invert borehole (subsurface) data, to drape the 2D (XY) survey geometries over 3D topography, the added ability to incorporate a-priori electrical resistivity or chargeability information by utilizing a 3D weighting function (which can be designed to emphasize or suppress some known spatial or directional features of the recovered model or otherwise, to force desired model conditions via property bound constraints), and interface weighting which can be used to define sharp contacts within the reference model (i.e. faults, unconformities, etc.) and laterally smoothing near surface variations in the recovered model.  

Boundary constraint is achieved by imposing restrictions on each cell in the mesh to have a model value of :math:`\mathbf{m}`, such that :math:`\mathbf{m}^l \leq \mathbf{m} \leq \mathbf{m}^u`, where the bounds :math:`\mathbf{m}^l` and :math:`\mathbf{m}^u`, the lower and upper bound, respectively, are prescribed by the user. The conjugate-gradient solution implements this through projected gradient techniques.

.. important:: This code is not meant to run inversions with underground air cells (e.g underground mine surveys)

Array types and Earth models
----------------------------

All linear survey surface-array types, including non-standard or uneven arrays, as well as their combinations can be inverted. There is no restriction on array geometry or electrode positioning, as long as the electrode locations are within the extent of the mesh. Recently, capability to invert borehole data and combined surface-borehole data sets has been added to the code. 

DCIPoctree considers the subsurface in terms of a mesh of rectangular cells. Numerical accuracy is increased with usage of smaller cells, but this also drastically increases the size of the problem. The idea behind usage of octree meshes is that in order to minimize the computational costs, the discretization of the volume should be adaptive, based on the quickness of recovered property transition in each direction. :numref:`mesh` shows an example of adaptive refinement for a circular structure. 

.. figure:: ../images/mesh.png
        :align: center
        :figwidth: 50%
        :name: mesh

When working with octree meshes, the underlying (base) mesh is defined as a regular 3D discretization with number of cells in each dimension equal to some power of 2. This underlying mesh is the finest possible discretization, which can be used in the inversion at any later stage, without using remeshing procedures. The idea is that if recovered model properties change slowly over a certain volume, then the cells bounded by this volume can be merged into a single cell without losing any accuracy in modelling, and only refined when the model begins changing. The spatial variability of model properties is a measure of the mesh refinement.

Program Library
---------------

The main executable programs within the DCIP octree program library are:

    - **create_octree_mesh_dcip:** creates an OcTree mesh based on the survey geometry
    - **dcipoctree_fwd:** used to forward model both DC and IP data
    - **surface_electrodes:** project surface formatted data to discrete surface topography
    - **dcsensitivity:** approximates the sensitivities for the DC or IP problem
    - **sens2weights:** creates sensitivity weights from sensitivities
    - **dcoctree_inv:** inverts DC data to recover a conductivity model
    - **ipoctree_inv:** inverts IP data to recover a chargeabitiliy model

The following Octree utility programs may also be helpful:

    - **blk3cellOct:** creates conductivity models on an OcTree mesh
    - **create_weight_file:** creates the weighting on each cell in the model
    - **interface_weights:** creates weights on the faces of cells


Licensing
---------

Licensing for commercial use is managed by distributors, not by the UBC-GIF research group.
Details are in the `Licensing policy document <http://gif.eos.ubc.ca/software/licensing>`__.


Installing
----------

There is no automatic installer currently available for this package. Please follow the following stesp in order to use the software.

#. Extract all files provided from the given zip-based archive and place them all together in a new folder such as

#. Add this directory as new path to your environment variables.

One additional note about installation:

-  Do not store anything in the "bin" directory other than executable applications and Graphical User Interface applications (GUIs).
