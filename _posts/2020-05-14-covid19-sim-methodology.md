---
layout: post
title: Agent Based Modeling Methodology for the COVID Interventions Analysis
subtitle: The complete methodology of how we accomplished the simulations using various tools.
gh-repo:
gh-badge:
tags: [Webscraping, NLP, Mapping]
comments: true
image: /images/blog/covid_sim_1/cover2.gif
reading-time: '7'
---

# Agent-Based Epidemiological Simulation
This project aims to determine and quantify the effects of implementing lockdown, mass testing, quarantine delays, and social distancing in controlling the spread of a disease. In particular, we focus on the effects of these interventions to the recovery and death rates. In this article, we will focused first on discussing the approach we took to model a simple epidemiological simulation using a technique known as agent-based modelling. This article will also discuss the tools used, as well as instructions on how to explore our model yourselves. A separate article will be dedicated to performing analysis on the simulation results.


## What is Agent-Based Modelling?
<img align="right" src="https://github.com/magoanalytics/agent-based-epidemiological-simulation/blob/master/pictures/interface.png?raw=true" width="450px" height="250px" />

Agent-based modelling (ABM) is a technique that models a complex system by reducing it to the interactions between agents and their environment. Here, agents can possess properties such as age and gender, and can perform actions based on pre-defined set of conditions. The environment possesses properties as well, and can affect the behavior of agents and vice versa. Observables such as population growth can then be measured to infer relationships between agent behavior and the overall behavior of the system. This makes ABMs powerful in that it can be used to observe and quantify the macroscopic behavior of many complex systems over time just by knowing how individual agents behave. This can be achieved without the need to construct differential equations that requires pre-existing knowledge of the relationships between observables.

Currently, there are a number of platforms that provide users with tools needed to build an ABM simulation. For this project, we'll be using Netlogo.

## Why Netlogo?
Netlogo is an open source, cross-platform multi-agent programmable modeling environment. Its user-friendly language allows users to quickly draft prototypes and visualize the results through an interactive customizable interface. In addition, Netlogo also includes dozens of pre-built models ranging from tumor growth simulation, to modelling behavior of gas particles. For more information, visit the official Netlogo site: https://ccl.northwestern.edu/netlogo/.

## Getting Started
#### Install Netlogo
To begin, you need to download the latest version of Netlogo using the following link: https://ccl.northwestern.edu/netlogo/download.shtml. When unpacked, a folder containing all the necessary files will be created. Open the Netlogo application file to launch.

## Clone Repository
Next, go to our repository using the link: https://github.com/magoanalytics/agent-based-epidemiological-simulation. After cloning the repository, load `epi_model.nlogo` from the file tab. Alternatively, you can simply double-click `epi_model.nlogo` from the repository folder.

## Setup and Go Procedures
Move the sliders and/or select values from the drop-down list in the interface tab to modify hyperparameters to their desired values, then click `Setup` button to initiate and update changes to the model. Click `Go` button to run the simulation.

![sample_interface](https://github.com/magoanalytics/agent-based-epidemiological-simulation/blob/master/pictures/interface.png?raw=true){: .center-block :}

For a complete list of hyperparameters, refer to the Model Parameters section.

## Modelling Approach
To model the spread of the disease in a population, we need to properly define the rules that govern how each agent behaves, as well as the interactions between the agents and its environment. In addition, agent behavior will have to be defined separately for simulations that include interventions. This section aims to explain our approach in detail.  

## Agent Behavior
<img align="right" src="https://github.com/magoanalytics/agent-based-epidemiological-simulation/blob/master/pictures/sample_agent.png?raw=true" width="200">

Agents are allowed to move around the world, infect other agents, recover, or die from the disease depending on the its current properties and surrounding environment. Agents can either be in the following states: `susceptible`, `infected`, `recovered`, or `dead`. To differentiate one state from the other, agents that are `susceptible`, `infected`, or `recovered` are colored green, red, and blue, respectively. The exception would be when an agent is considered `dead`, in which case the agent is removed from the simulation entirely.

At each tick, here defined to be an hour, agents are allowed to move in a random direction. If a `susceptible` agent is near an `infected` agent, the latter has a probability of being infected equal to its susceptibility. Here, susceptibility is an agent-level parameter that is used to model a person's hygiene, where a higher `susceptibility` value corresponds to lower hygenic behavior. On the other hand, if an infected agent has been sick for more than or equal to its `recovery-time`, it has a probability of recovering equal to its `recovery-rate`. However, at each tick, an infected agent also has a probability of dying equal to its `death-rate`.

It is assumed that agents that have recovered gain full immunity, and therefore cannot be infected twice.

## Environment
<img align="left" src="https://github.com/magoanalytics/agent-based-epidemiological-simulation/blob/master/pictures/sample_envi.png?raw=true" width="325">

The environment is where the simulation takes place. This is composed of an NxN grid boxes of equal area called `patches`. Each patch can either be a `normal` patch, `border` patch, or a `quarantine` patch. To differentiate these patches, the `border` patches are colored dark yellow while `quarantine` patches are colored light yellow. `Normal` patches are colored black.

`Border` patches divide the environment into areas that can represent a town or even an entire city. `Quarantine` patches can be found at the center. Infected agents that are quarantined are not allowed to leave the area in order to prevent them from further spreading the disease.

For completeness, it is worth noting that the environment is modelled to be bounded, or where wrapping is not allowed. This prevents agents from travelling from the edge of the world to the other edge of the world instantaneously.

Next, we discussed the interventions included in the model.

## Lockdown
During lockdowns, agents have a probability of crossing border patches equal to the `lockdown-intensity` value. This allows us to simulate not only complete lockdowns, but also those that are partially implemented.

## Quarantine and Isolation
<img align="right" src="https://github.com/magoanalytics/agent-based-epidemiological-simulation/blob/master/pictures/sample_quarantine.png?raw=true" width="200">

Every 24 ticks, each agent has a probability of being test equal to the `mass-testing-intensity` value. This allows us to simulate mass testing, where everyone is tested regardless of whether the person is showing symptoms or not, as well as simulating testing done on a much smaller scale. To simulate the delay between a person being tested positve to when the person is quarantined, an additional parameter is added named `quarantine-delay`, which ranges from one day to up to one week. An agent that is quarantined is transferred to an isolated area in order to prevent the agent from infecting other agents.

## Social Distancing
To quantify the effects of distancing oneself from other people, the parameter named `social-distancing-intensity` is added. Each agent has a probability of maintaining a fixed distance from the agent nearest to it equal to the value of this paramter. This allows us to simulate the behavior of the entire system for cases where everyone complies with social distancing and where only a portion of people do.

## Model Parameters
To determine their effects, a set of parameters is assigned to each intervention. These parameters can be turned "on" or "off" by setting them to higher or lower values to increase or decrease their effects, respectively. For example, to isolate the effectiveness of lockdown, one can increase the `lockdown-intensity` factor while setting the parameters `mass-testing-intensity` and `social-distancing-intensity` to 0. The overall effectivess of combined interventions can also be explored by adjusting the appropriate parameters.
The table below lists the hyperparameters, together with a short description and possible values, that can be adjusted in the interface tab:

|Model Parameter|Description|Value|
|-|-|-|
|initial-populatin|Initial number of agents at the start of the simulation (t = t<sub>0</sub>)|[10,5000]|
|initial-infected|Initial number of infected agents at the start of the simulation (t = t<sub>0</sub>)|[1, 10]|
|average-susceptibility|Average probability of a person being infected when near infected agent(s)|[0, 100]|
|average-recovery-rate|Average probability of an infected agent to recover|[0, 100]|
|average-recovery-time|Average time needed for an agent to have a chance to recover after being infected|{336, 504, 672}|
|average-death-rate|Average probability of an infected agent dying|[0, 1]|
|lockdown-intensity|Average probability of an agent attempting to cross border to cross successfully|[0, 100]|
|mass-testing-intensity|Probability of an agent being tested every 24 hours|[0, 100]|
|quarantine-delay|Number of days before infected agent is quarantined after being tested positve|[1, 7]|
|social-distancing-intensity|Probability of an agent to observe social distancing|[0, 100]|

<br>

## Next Steps
Now that we have a better understanding of the modelling approach, we can proceed to perform simulation runs and do analysis. On our next article, we'll be focusing on analyzing and quantifying the effects of the above mentioned interventions to the infection, recovery, and death rates.
