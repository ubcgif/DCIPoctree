.. _example_fwd_surface:

Forward Modeling
================

Here, the code **dcipoctree_fwd.exe** and the input file **dcip_fwd.inp** (:ref:`see format <dcip_input_fwd>`) are used to forward model DC and IP data along 9 pole-dipole profile lines oriented West to East. Files relevant to this part of the example are in the sub-folder *fwd*. For this example, we use the models that were created in the example ":ref:`create model<example_model_surface>`". Before running this example, you may want to do the following:

	- `Download and open the zip folder containing the entire DCIP octree example <https://github.com/ubcgif/DCIPoctree/raw/master/assets/dcipoctree_example_surface.zip>`__ (if not done already)
	- :ref:`Learn how to run code from command line <dcip_fwd>`
	- :ref:`Learn the format of the input file <dcip_input_fwd>`


To forward model the data, the following input file was used. Because the survey file (**survey_xy.loc** ) uses a surface format, any electrodes located in air cells are automatically projected to the discrete surface topography defined by the :ref:`active cells model <activeFile>`.

.. figure:: images/fwd_input.png
     :align: center
     :width: 700

By choosing the *IPL* flag on the first line of the input file, we are modeling DC and IP data. And a linearized formulation for modeling the IP data is used. The DC data are the measured voltage normalized by the transmitter current (V/A). The code also outputs the corresponding apparent resistivity values. The IP data are the IP voltage normalized by the DC voltage (V/V). Below, we show the 2D pseudo-sections for data collected along profile line 5 (Northing = 0 m).

**Voltage Data (V/V)**

.. figure:: images/fwd_V.png
     :align: center
     :width: 700

**Apparent Resistivity (Ohm m)**

.. figure:: images/fwd_rho.png
     :align: center
     :width: 700

**Apparent Chargeability (V/V)**


.. figure:: images/fwd_ip.png
     :align: center
     :width: 700

