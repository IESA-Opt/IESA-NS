# IESA-NS

IESA-NS (Integrated Energy System Analysis for the North Sea region) is an open model developed within the IESA-Opt framework. The IESA-NS model covers seven North Sea countries (Belgium, Denmark, Germany, the Netherlands, Norway, Sweden and the United Kingdom), the offshore geographical representation on the IESA-NS model is modular, so the user can represent the offshore part of the region with as many different offshore nodes as required.

This repository is still under construction. If you have any question please contact R.Martinez.Gordon@rug.nl

The IESA-NS model has been part of the following peer reviewed publications:

   R.Martinez-Gordon, M. Sanchez-Dieguez, A. Fattahi, G.Morales-España, J.Sijm, A.P.C Faaij, "Modelling a highly decarbonised North Sea energy system in 2050: a multinational        approach", Advances in Applied Energy, 2022, doi.org/10.1016/j.adapen.2021.100080

All the scenario outputs of the IESA-NS publications can be consulted in https://iesa-opt.shinyapps.io/NS_Paper1/ via the 'local scenario files'

# Model description

The IESA-NS model is a cost-optimization model, formulated as an LP, that optimizes the long term investment planning and short term operation of the NSR energy system. The model can optimize multiple years simultaneously, accounts for all the national GHG emissions and includes a thorough representation of all the sectors of the energy system.

The IESA-NS model has been developed based on the IESA-Opt framework. The IESA-Opt model was initially developed to cover in detail the energy system of the Netherlands, filling multiple knowledge gaps that most integrated energy system models in the literature present. 

Additional information and more details about assumptions, background and relevant sources can be found in the IESA-Opt methodological publications:

doi.org/10.1016/j.adapen.2021.100043
doi.org/10.1016/j.adapen.2021.100009

The IESA-NS model is a cost-optimization model, formulated as a linear problem (LP), that, in short, optimizes the long term investment planning and short term operation of the NSR energy system. The model can optimize multiple periods simultaneously (and therefore can be used to analyse single year optimization scenarios or transition pathways towards 2050), accounts for all the national GHG emissions and includes a thorough representation of all the sectors of the energy system.

![image](https://user-images.githubusercontent.com/95577314/145430378-82fb3f50-2316-4b9d-8699-764598fe00ad.png)

there are mainly 6 different required inputs: activity demands, driven by macro-economic data; technology data in order to create the technology portfolio; available potentials of multiple resources and technologies; primary energy prices; national mitigation targets and specific technology bans; and finally data for the European power system, which is also endogenously represented in the system.

As mentioned, the IESA-NS model is formulated as an LP, whose objective function comprises the minimization of investments cost, retrofitting costs, decommissioning costs and both fixed and variable operation costs. The formulation presents a wide range of constraints to ensure that the optimal system configuration is feasible and respects different physical and theoretical boundaries.

One of the interesting features of the IESA-NS model is that its formulation includes different temporal resolutions. The power sector and the heat networks are optimized with hourly resolution, allowing to properly capture the intermittency of variable renewable sources, and the dynamics of short and long term energy storage, among others. The multiple cross-sectoral flexibility options that the model includes (e.g. demand shedding, load shifting, flexible CHPs) are also formulated with hourly resolution. The gas and hydrogen network are modelled using daily resolution. Finally, some other constrains are formulated with yearly resolution, like the activity balance (i.e. the system should satisfy all the exogenous demands driven my macro-economic trends), certain system capacities, retrofitting decisions or the technology lifetimes. 

The optimization process provides a plethora of direct results, like the optimal objective function value, all the technology stocks and their operation levels, the investment, retrofitting and decommissioning decisions, the operation of the flexible technologies, including their deviation from their reference profiles, the different energy prices, and all the CO2 shadow prices. Moreover, the IESA-NS model includes a thorough post processing that permits to analyse, among others, the energy balances, system costs, use of renewables, emissions, levelized costs of electricity (LCOE), hourly power dispatch in every node of the system, imports and exports dynamics, curtailment and electrification levels, and many more. All the data can be visualized in the tailor-made online user interface of the model.

As mentioned, the IESA-NS model is defined by activities and technologies. The activities are exogenous parameters, linked to macro-economic data and estimations, while the technologies are the tools that the model has to satisfy these activities.

 ![image](https://user-images.githubusercontent.com/95577314/145430540-74d548f4-6292-4bce-a748-3680aea511d0.png)
 
 There are different activities that are part of each country of the NSR in the IESA-NS model. The driver activities are the exogenous demand volumes corresponding to the residential, services, agriculture, industry and transport sector, together with aggregated emissions not fully contained in the energy system (and modelled with MACC curves). The model, with these demand volumes, decides which of the available technologies should be used to satisfy these demands. The use of technologies entails (sometimes) direct CO2 emissions, and certain energy requirements (either primary energy or processed energy). This processed energy has to be provided by endogenous energy activities, and the model has also to select which process is optimal to do so. For example: if there is an exogenous transport demand, and the model decides to satisfy it with an electric car, there will be an endogenous demand for electricity to power this car. Therefore, the model has to decide which process is optimal in order to supply this electricity.
 

