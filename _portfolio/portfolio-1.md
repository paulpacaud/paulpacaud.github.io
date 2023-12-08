---
title: "Forecasting the solutions space of Power Net Exportations as a function of weather data"
excerpt: "As a quantitative researcher at Engie, I've built a ML model forecasting the feasile sets of Power Net Exportations in Europe satisfying the European Power Grid constraints. <br/><img src='/images/solutions_space.gif'>"
collection: portfolio
---

In the European power market, everyday electricity price is calculated for the day-ahead. Supply and demand are forecasted for the day-ahead: the point at which the two curves intersect represents the market-clearing price. Given a forecasted power demand, the power operators run an optimization solver that aims at minimizing production costs with respect to the constraints of meeting the demand, and the constraints of the power grid.

In their day-to-day job, the goal of quantitative traders boils down to forecasting the power price. To do so, they need to have all the parameters used in the power market optimization problem. That's where I come into the picture. I've helped my team better understand the power grid constraints, with vizualisation tools and I created a ML model to forecast these constraints as a function of weather data.

Due to physical laws and limited transmission capacities, the power net exportations of each country in Europe is bound by the grid following this set of constraints:

$$ \sum_{z \in CWE} PTDF_{z,cb} \cdot nex_z \leq RAM_{cb} \quad \forall cb \in CB. $$

- $$CB$$ represents the set of critical branches (=lines) of the power grid.
- $$CWE$$ is the set of zones within the market (France, Belgium..).
- $$n_{ex_z}$$ stands for the net export of electricity of zone z.
- $$PTDF_{z,cb}$$ is the Power Transfer Distribution Factor for zone $$z$$ on the critical line $$cb$$ (see it as a tool used by system operators to predict how changes in one part of the network will affect the rest of the system).
- $$RAM_{cb}$$ represents the Reliability Margin on critical lines (see it as the physical limitation of the line).

The points satisfying this set of constraints are called the feasible solutions of the constraints set. The resulting solutions space is in the form:

$$ { N_{ex} \in R^{14} : PTDF.N_{ex} \leq RAM } $$

This solutions space is a convex polyhedron: a 14-dimensional space whose boundaries are formed by hyperplanes. To visualize a 2D cut of this polyhedron, I created a visualization of the cut Net Export France->Belgium (FR->BE) // Net Export France -> Germany (FR->DE). I represented the evolution of this solutions space over time in 2023:

<img src='/images/solutions_space.gif'>

Why does this solutions space evolve over time ? As the weather changes over the year, the supply (wind turbines, hydraulic dams, solar panels) changes and the consumption (heating, industry..) also. I therefore built a Python ML pipeline to forecast the evolution of the shape of this polygon as a function of weather data. The details are not shareable as it is a confidential project.
