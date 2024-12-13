---
title: "Characterizing the 14-dimensional solutions space of the power market optimization problem"
excerpt: "As a quantitative researcher at Engie, I've built a ML model forecasting the feasible sets of Power Net Exportations in Europe satisfying the European Power Grid constraints. <br/><img src='/images/01_04_2023_21.png'>"
collection: portfolio
---

I have worked for one year in the quantitative trading team of Engie, on various topics related to Power and Gas Market. Even tough I can't disclose the methods used in my company, I can still give you an overview of the kind of optimization problems I've been working on.

### Introduction
Every day in the European power market, electricity prices are set for the next day based on forecasted supply and demand. The intersection of these two curves determines the market-clearing price.
Every day, Power Operators have to plan which power plants to turn on the next day to meet the forecasted demand. To decide, they run optimization algorithms to minimize production costs while adhering to both demand requirements and power grid constraints.

In this dynamic market, quantitative traders aim to predict power prices, a task requiring a deep understanding of the parameters influencing the power market optimization problem. That's where I come into the picture. I've helped my team better understand the power grid constraints, building visualization tools and an ML model.

### Problem Formulation
Due to physical laws and limited transmission capacities, the power net exportation of each country in Europe is restricted by the grid through this set of constraints:

$$ \sum_{z \in Zones} PTDF_{z,cb} \cdot nex_z \leq RAM_{cb} \quad \forall cb \in CB. $$

- $$CB$$ represents the set of critical branches (=lines) of the power grid.
- $$Zones$$ is the set of zones within the market (France, Belgium..). There are 14 zones, which is why we deal with a 14-dimensional problem.
- $$n_{ex_z}$$ stands for the net export of electricity of zone z.
- $$PTDF_{z,cb}$$ is the Power Transfer Distribution Factor for zone $$z$$ on the critical line $$cb$$ (see it as a tool used by system operators to predict how changes in one part of the network will affect the rest of the system).
- $$RAM_{cb}$$ represents the Reliability Margin on critical lines (see it as the physical limitation of the line).

The Net Exports satisfying this set of constraints are called the feasible solutions of the constraints set. Noting $N_{ex}$ the 14*1 vectors of possible net exports, the ones that are in the solutions space are defined by:

{ $$ N_{ex} \in R^{14} : PTDF.N_{ex} \leq RAM $$ }

The feasible solutions, or Net Exports, satisfying to these constraints form a convex polyhedron in a 14-dimensional space.  Visualizing a 14-dimensional object is not feasible, but we can examine its 2D facets. For example, consider the facet representing net exports between France and Belgium (FR->BE) and France and Germany (FR->DE). I've created the animated image below to showcase the evolution of this solution space in 2023. The feasible area is highlighted in blue, with each line representing a constraint. The actual solution is depicted as a green point.
<br/><img src='/images/solutions_space.gif'>

### My work

I worked on modeling this very hard problem that is not solved in the literature.