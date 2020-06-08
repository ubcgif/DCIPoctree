.. _example:

.. warning:: This manual contains the documentation for DCIP octree package releases **beginning on 2020-05-08**. This version of the package is compatible with GIFtools v2.31 and later. If using an earlier version of GIFtools, please see the `2014-10 release manual <https://dcipoctree.readthedocs.io/en/2014-10/>`__ .

Examples
========

Here, the program libraries for DCIP octree will be used to:

    - create an Octree mesh based on the survey
    - create octree models
    - DC and IP data for conductivity and chargeability models, respectively
    - create sensitivity weights model
    - create interface weights
    - invert DC and IP data to recover conductivity and chargeability models, respectively

Zip folders containing all necessary files can be downloaded here:

    - `Download and open the zip folder containing the entire DCIP octree example <https://github.com/ubcgif/DCIPoctree/raw/master/assets/dcipoctree_example.zip>`__

The full examples are parse into 5 sections:

.. toctree::
    :maxdepth: 2

    Create octree mesh <example/create_octree>
    Create octree model <example/create_model>
    Forward modeling <example/fwd>
    Sensitivity weights <example/sensitivity_weights>
    Interface weights <example/interface_weights>
    Inversion <example/inv>

