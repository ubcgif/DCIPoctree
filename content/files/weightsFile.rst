.. _weightsFile:

Cell and Face Weights File
==========================

Cell Weights
------------

Cell weights files have the same format as :ref:`model files <modelFile>`. When creating cells weights:

    - All cells must be assigned a weight values larger than 0! This is to ensure the problem is sufficiently well-conditioned.
    - Model weight values should be set relative to a value of 1. This is to ensure the relative emphasis on model weights and surface weights is preserved. A value of 1 implies that no cell weighting is being applied.
    - Large model weights (:math:`w \gg 1` ) are used for cells that we want to match the reference model.
    - Small model weights (:math:`w \ll 1` ) are used for cells to reduce the impact of the reference model on the cells.


Interface Weights
-----------------

Interface weights files contain the interface weights in x, y and z in a single column vectors; as the number of faces in x, y and z may differ. When creating interface weights:

    - All interface weights must be larger than 0! This is to ensure the problem is sufficiently well-conditioned.
    - Interface weight value should be set relative to a value of 1. This is to ensure the relative emphasis on model weights and surface weights is preserved. A value of 1 implies that no interface weighting is being applied.
    - Large interface weights (:math:`w \gg 1` ) preserve gradients within reference model.
    - Small interface weights (:math:`w \ll 1` ) results in smoother gradients within
















