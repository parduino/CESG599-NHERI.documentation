.. _case_4:

S\ :sup:`3` hark - Site Response 2
==================================

Author: Chungen Tai
(Updated : 05/24/24)
-------------------

Introduction
------------

This page shows basic concepts of one-dimensional nonlinear site response analysis by using various soil material models (ex: ElasticIsotropic, PM4Sand.).Site response analysis is commonly performed to analyze the propagation of seismic waves through soil. As shown in the below figure, one-dimensional response analyses, as a simplified method, assume that all boundaries are horizontal and that the response of a soil deposit is predominately caused by SH-waves propagating vertically from the underlying bedrock. Ground surface response is usually the major output from these analyses, together with profile plots such as peak horizontal acceleration along the soil profile. When liquefiable soils are presenting, maximum shear strain and excess pore pressure ratio plots are also important.

.. figure:: ./images/siteResponse2.png
    :scale: 60 %
    :align: center
    :figclass: align-center

Problem Description
-------------------

Treasure Island, situated atop sand fill strata overlaying Bay Mud within the San Francisco Bay, was subjected to seismic activity during the 1989 Loma Prieta Earthquake. Adjacent to Treasure Island lies Yerba Buena Island, characterized by its natural rock outcrop. Utilizing the site's soil profile and seismic data recorded on Yerba Buena Island, we endeavor to analyze the site response of Treasure Island. This entails computing parameters such as peak horizontal acceleration and shear strain distribution along the soil profile. Furthermore, we aim to investigate the influence of varying slope configurations on the site's response characteristics. 



Solution Strategy
-----------------

#. Open the Dr. Layer program. By default we get twelve layers. The top six layers are hardwired into the system with a velocity of specified as very fast. The bottom six layers are hardwired with a velocity of very slow.

#. Select all the layers to all have very slow values using the select all option.

#. On the top left hand corner of the menu box choose the plot box tool and apply a plot box at the top of the layers. Do the same at four arbitrary points along the soil layers. Note the height (:math:`H`) you place the plots.

    <insert image>

#. Push the time increment button for about 1 minute.

#. Obtain the angular frequency :math:`(2p/T)`, where :math:`T` is the period i.e. time it takes to complete one revolution.

#. Obtain the maximum displacements from the plots by clicking on the crest of the curves with your cursor.

.. math::
    TF = \frac{1}{\cos(\frac{wH}{v_s})}

    AF = \frac{1}{|\cos(\frac{wH}{v_s})|}


Where

:math:`w` = Angular frequency (2pf)

:math:`H` = distance between any two points in the layers under consideration.

:math:`V` = Velocity of wave travel within the soil layer.

:math:`TF` = Transfer function

:math:`AF` = Amplification function


Dr. Layer's operation is controlled via menu commands (with associated keyboard accelerators), manipulation tools, scaling buttons, the load tool bar, and time control buttons. The program displays the results of its calculations visually in the form of animated displacements, and also in the form of dynamically generated time history plots. There are also mechanisms for getting numerical values.

.. figure:: ./images/case1.png
    :scale: 30 %
    :align: center
    :figclass: align-center


SimCenter Tool Used
-------------------

blablabla

.. list-table:: Title
   :widths: 25 25 50
   :header-rows: 1

   * - Heading row 1, column 1
     - Heading row 1, column 2
     - Heading row 1, column 3
   * - Row 1, column 1
     -
     - Row 1, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3

Time can be controlled using either the keyboard or the time control buttons:

* To run time **forward**: Press and hold the 'g' key or click and hold the time forward button: <insert icon>.

* To reset time to **zero**: Type the '0' key or click on the time reset button: <insert icon>.

* The current analysis time is **displayed** in the feedback pane at the bottom of the screen.

* The analysis time step size can be controlled via the Time Step menu (there are combinations of material properties and time steps that intentionally lead to unstable results, so beware).

* The display time step can be controlled via the Animation Speed menu. Internally, this command controls how many analysis time steps are computed between screen updates.


Example Application
-------------------

Dr. Layer's tool palette is illustrated below (Windows version: the Mac version is similar but grouped a bit differently):

<insert tool palette image>

* The **Arrow Tool** is used to select and manipulate objects.

* The **Panner** and **Camera Orbit Tools** are used to change the viewing point and camera orientation via clicking and dragging.

* The **Plot Box Tool** is used to create one of the various types of plot boxes: 

    * **Displacement Time History plots** are created by clicking on the relevant layer. The top node in the layer is used as the plotting target.

    * **Fast Fourier Transform (FFT) plots** of a displacement history can be created by clicking on the time history plot.

    * **Stress-strain plots** can be created by control-clicking (i.e., holding down the control key while clicking) on the desired layer.


 These controls are self-explanatory in regards to their functions. Note the following, however:

.. note::
    The scaling buttons will continue to scale as long as they are held down. It is not necessary to click multiple times to get this effect.


Remarks
-------

* To adjust the **plotting scales**, use the small expansion/contraction triangular buttons on the plot for the horizontal scale, and the plot scale buttons on the `Scale Button Toolbar <#scaling-buttons>`_ for the vertical scale. 

.. note::
    You will notice that all plots scale together. This is so that plots of a given type can be compared visually without any misleading differences in scale factors.

* To adjust the **horizontal offset** of a plot, click in the plot and drag horizontally to scroll back and forth.

.. note::
    In general, plots will automatically scroll as necessary as time is running. Once you have manually scrolled a plot, though, the automatic scrolling will cease until time is reset to zero.

* Plot boxes can be added or removed at any time, but they only accumulate data beginning from the time they are installed, with the exception of FFT plots, which always plot the according to the data accumulated in the target time history. FFT plots can use up to the first 1024 points in a time history.


.. warning:: 
    Plotting FFT's will slow down the animation speed significantly, especially as the length of the time histories increase.

.. bibliography:: references.bib
