.. _example:

.. warning:: This manual contains the documentation for DCIP octree package releases **beginning on 2020-05-08**. This version of the package is compatible with GIFtools v2.31 and later. If using an earlier version of GIFtools, please see the `2014-10 release manual <https://dcipoctree.readthedocs.io/en/2014-10/>`__ .

Examples
========

Here, the program libraries for DCIP octree will be used to:

    - create an OcTree mesh based on the survey
    - construct block models on OcTree meshes
    - DC and IP data for conductivity and chargeability models, respectively
    - create interface weights
    - create sensitivity weights model
    - invert DC and IP data to recover conductivity and chargeability models, respectively


Surface Data Example
--------------------

In this example, we simulate and invert DC/IP data with survey/observations files that are in 'surface format'. That is, electrode elevation columns are not included in the survey/observations files and we assume all electrodes live on the discretize surface topograpy.

Zip folders containing all necessary files can be downloaded here:

    - `Download and open the zip folder containing the entire DCIP octree example <https://github.com/ubcgif/DCIPoctree/raw/master/assets/dcipoctree_example_surface.zip>`__

The full examples are parse into 6 sections:

.. toctree::
    :maxdepth: 2

    Create octree mesh <example_surface/create_octree>
    Construct octree model <example_surface/create_model>
    Forward modeling <example_surface/fwd>
    Interface weights <example_surface/interface_weights>
    DC Inversion <example_surface/dcinv>
    IP Inversion <example_surface/ipinv>


General Data Example
--------------------

In this example, we simulate and invert DC/IP data with survey/observations files that are in 'general format'. That is, columns for the electrode elevations are included in the survey/observations files. However, we must ensure an electrodes located above the discrete surface topograpy are projected to the discrete surface so they are not modeled as living in the air.

Zip folders containing all necessary files can be downloaded here:

    - `Download and open the zip folder containing the entire DCIP octree example <https://github.com/ubcgif/DCIPoctree/raw/master/assets/dcipoctree_example.zip>`__

The full examples are parse into 6 sections:

.. toctree::
    :maxdepth: 2

    Create octree mesh <example_general/create_octree>
    Construct octree model <example_general/create_model>
    Forward modeling <example_general/fwd>
    Interface weights <example_general/interface_weights>
    Project Electrodes to Surface <example_general/surface_electrodes>
    DC Inversion <example_general/dcinv>
    IP Inversion <example_general/ipinv>