---
layout: post
title: "Plotting Molecular Electrostatic Potential Maps in IQmol"
description: "An example calculation on pyridine using PSI4 and IQmol"
categories: ["computational", "chemistry", "tutorial", "electrostatic", "potential", "PSI4", "IQmol"]
location: "Galaxy far far away"
---

Undoubtedly any student of chemistry is familiar with molecular electrostatic potential (ESP) plots, the colorful diagrams that litter organic chemistry textbooks showing the distribution of charge in a molecule. These diagrams are extremely useful for predicting likely sites of electrophilic and nucleophilic attack in reaction mechanisms. 

This blog post will focus on how to calculate the ESP in PSI4 and render electrostatic potential maps in IQmol. For this example we will produce an ESP plot for pyridine. The first place to begin is to obtained an optimized geometry, well use a modest level of theory using MP2/6-31G(d). Once you have an optimized structure, you can make use of a utility called cubeprop in PSI4 that produces cube files of various properties such as the electrostatic potential, orbitals, densities, etc. The input file I used for this calculation is shown below.

{% include image.html url="../../../../images/psi4_inp.PNG" caption="" width="600px" align="center" %}  

There are two major differences from your standard PSI4 energy input that allows for the production of cube files. The first is an additional set option called cubeprop_tasks it is here that you can pass an array of options to the cubeprop function letting it know what types of cube files you want to produce. Since we only want the electrostatic potential, we simply pass it the ESP option. Finally, the call to the energy function at the end of the input is very different. Youre going to pass an option to the energy function allowing it to return the wavefunction (return_wfn=True) and then we will store that wavefunction in the wfn variable. Finally you pass that wavefunction to cubeprop and let it do its thing. If the calculation runs successfully, you should now have an ESP.cube file in your current directory, thats the cube file of the electrostatic potential that you will need. Now lets fire up IQmol and start plotting.

When you open up IQmol go under file and open to grab your cube file from your directory, it should open and show your molecule. (Note: if you want a white background like the one shown in my screenshots, you have to go under the Global drop down menu and then uncheck the box for background). 

{% include image.html url="../../../../images/iqmol_1.PNG" caption="" width="600px" align="center" %}  

What we want to do first is plot the cube file, double clink the box that says Cube Data and it should bring up the following pop-up menu:

{% include image.html url="../../../../images/iqmol_2.PNG" caption="" width="300px" align="center" %}


Pick your isosurface value and then press Calculate, this should bring up a plot that looks like this:

{% include image.html url="../../../../images/iqmol_3.PNG" caption="" width="600px" align="center" %}  

Clearly this doesnt yet look like an electrostatic potential plot, by default IQmol will plot the cube file where positive values are solid blue and negative values are solid red. This is the convention used for orbital plots, but for plotting an ESP, we want to use a spectrum of colors and not simply the binary choice of red or blue. To change this, expand the drop down menu for Cube Data and double click the checked box that should say Cube Data, this will bring up the Configure Surface menu. Simply change the Property to ESP (Gasteiger) and you now have a color spectrum. 

{% include image.html url="../../../../images/iqmol_4.PNG" caption="" width="300px" align="center" %}  

I prefer to change the endpoint values, you can click on them and change them to whatever you want. From my experience a range of -0.05 to +0.05 produces good looking plots. Click OK and you now have your potential map!

{% include image.html url="../../../../images/iqmol_5.PNG" caption="" width="600px" align="center" %}  


If you dont like the red and blue option and prefer a blue, yellow, green, orange spectrum that is an option as well. Return to the Configure Surface menu and simply double click on the color gradient and choose spectrum and you will have your wish:

{% include image.html url="../../../../images/iqmol_6.PNG" caption="" width="600px" align="center" %}  

I only recently found IQmol, and Im really loving this program. I used to use a combination of Avogadro and VMD for these sorts of tasks, but the simplicity of use for IQmol is winning me over. And the ESPs look really good too!
