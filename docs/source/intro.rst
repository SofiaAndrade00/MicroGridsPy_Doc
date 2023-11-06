
.. image:: https://raw.githubusercontent.com/SESAM-Polimi/MARIO/767d2c0e9e42ae0b6acf7c3a1cc379d7bcd367fa/doc/source/_static/images/polimi.svg
   :width: 200
   :align: right
   
#######################################
Introduction
#######################################
What is MicroGridsPy
=========================================
MicroGridsPy is a bottom-up, open-source optimization model, running on `Pyomo <https://pyomo.readthedocs.io/en/stable/>`_, a Python library used to model optimisation problems, whose primary goal is to offer an open-source approach to the issue of energy scaling and dispatch in mini-grids in remote locations. It was first developed in 2016 by the University of Liege and the code is freely available on GitHub. The model enables the optimization of micro-grid size and its dispatch strategy at the 1-hour temporal resolution, also returning as output the fixed and variable costs associated with each technology and the LCOE of the system. It is based on Linear Programming, and it enables the choice of the installed capacities of batteries, generators, and renewable energy sources that result in the lowest Net Present Cost (NPC) or lowest Operation and Maintenance expenses (O&M) during the project's lifespan while achieving the system limitations. However, in the latest version, it is also possible to consider a multi-objective optimization such as costs and emissions to model different scenarios with different drivers like environmental impact and not only economic parameters. The main inputs required by the tool to initialize the variables and formulate linear constraints, as shown in the figure below, are time series of load demand at 1-hour resolution for one year (or more years); time series of RES production at 1-hour resolution for one year; techno-economic parameters of the technologies and project parameters. In this context, it must be said that in the latest version of MicroGridsPy already structured load demand archetypes referring to rural villages in Sub-Saharan Africa at different latitudes are integrated into the model, from which the code directly derives the time series of load profile. Moreover, an endogenous calculation of RES production times series, solar and wind, relying on the NASA POWER platform is now possible. In the most recent version, there is also the possibility of simulating the connection of the mini-grid with an existing main grid by detailing electricity flows in both directions (electricity taken from the grid or fed into the grid), as well as the availability of the national grid in the event of blackouts.

Why it is developed
=========================================
MicroGridsPy is inspired by the other existing energy system optimization models 
particulary `OSeMOSYS <http://www.osemosys.org/>`_ by [Howells2011]_, 
`Calliope <https://calliope.readthedocs.io/en/stable/user/introduction.html>`_ by [Pfenninger-Pickering2018]_
and `TIMES <https://iea-etsap.org/index.php/documentation>`_ by [Loulou2005]_.
It is designed to compelete the path of these frameworks by addressing the main 
challenges of the modern energy system modelling frameworks that are shortly explained in the following:

* **Dynamic annual investments on the energy system:** With the aim of
  exploring the possible evolution of the energy systems in the transition pathways,
  the energy modeling frameworks need to cover both the operation and planning modes by simulateneously 
  delivering the required dynamic annual capacity expansions and full hourly dispatch of different technologies within the energy systems. 
  However, most of the existing models with high temporal resolution are falling
  short of delivering all the required annual investments in the long-term horizons and just
  follow a snapshot approach for estimating the required new capacities to be installed for the future growths in the final demand.


* **Resolution in time:** On the other hand, most of the planning models are not computationally
  able to include fine temporal resolutions down to hourly timesteps within each modelling year
  of the time horizon. Therefore, they may deliver inaccurate results due to missing the full variability
  of the both demand and supply sides of the energy system.
  
* **Resolution in space:** The concept of spatial resolution contains not only the ability of
  representing multiple regions in different dimensions but also the possibility to model the 
  interconnections among various regions by modelling the inter-regional transmission links.
  
* **Sector coupling:** The interactions and synergies among different sectors of the energy system
  must be considered in the energy modelling frameworks by following a comprehensive technology definition
  similar to all the above mentioned models.
    
* **Transparency:** The concept of transparency and opennes has manifold aspects. The open science
  approach for an energy model is not only about publishing the governing structures and equations but also
  following several critieria such as:
  
  * Convenient access to source code, data and assumptions
  * Providing understanble input data structure not only for the experts but also for any potential user
  * Clear and modular core code
  * Flexible source code to any possible future modification and integration

Acknowledgement
=========================================

* The development of MicroGridsPy was not possible without the kind attention and help of Professor
  `Emanuela Colombo <https://www4.ceda.polimi.it/manifesti/manifesti/controller/ricerche/RicercaPerDocentiPublic.do?EVN_DIDATTICA=evento&k_doc=44891&lang=EN&aa=2014&tab_ricerca=1>`_.
  We are fully grateful for having the chance to work under her supervision and would like to express our gratitude for her unwavering support.

* We would also like to acknowledge `Steve Dimond <https://stevediamond.github.io/WWW/>`_ for his kind support and guide that allows us to better understand and use CVXPY for this framework
    
License
========

.. image:: https://img.shields.io/badge/License-Apache_2.0-blue.svg
    :target: https://www.apache.org/licenses/


This work is licensed under `Apache 2.0 <https://www.apache.org/licenses/>`_

References
=========================================
.. [Diamond2016] Diamond, S., & Boyd, S. (2016). CVXPY: A Python-embedded modeling language for convex optimization. The Journal of Machine Learning Research, 17(1), 2909-2913.
.. [Howells2011] Howells, M., Rogner, H., Strachan, N., Heaps, C., Huntington, H., Kypreos, S., ... & Roehrl, A. (2011). OSeMOSYS: the open source energy modeling system: an introduction to its ethos, structure and development. Energy Policy, 39(10), 5850-5870.
.. [Pfenninger-Pickering2018] Pfenninger, S., & Pickering, B. (2018). Calliope: a multi-scale energy systems modelling framework. Journal of Open Source Software, 3(29), 825.
.. [Loulou2005] Loulou, R., Remme, U., Kanudia, A., Lehtila, A., & Goldstein, G. (2005). Documentation for the times model part ii. Energy Technology Systems Analysis Programme.


