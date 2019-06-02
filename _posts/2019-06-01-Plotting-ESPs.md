---
layout: post
title: "Plotting Molecular Electrostatic Potential Maps in IQmol"
description: "An example calculation on pyridine using PSI4 and IQmol"
categories: ["computational", "chemistry", "tutorial", "electrostatic", "potential", "PSI4", "IQmol"]
location: "Galaxy far far away"
---

Undoubtedly any student of chemistry is familiar with molecular electrostatic potential (ESP) plots, the colorful diagrams that litter organic chemistry textbooks showing the distribution of charge in a molecule. These diagrams are extremely useful for predicting likely sites of electrophilic and nucleophilic attack in reaction mechanisms. 

This blog post will focus on how to calculate the ESP in PSI4 and render electrostatic potential maps in IQmol. For this example we will produce an ESP plot for pyridine. The first place to begin is to obtained an optimized geometry, well use a modest level of theory using MP2/6-31G(d). Once you have an optimized structure, you can make use of a utility called cubeprop in PSI4 that produces cube files of various properties such as the electrostatic potential, orbitals, densities, etc. The input file I used for this calculation is shown below.


