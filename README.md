<Image src="https://user-images.githubusercontent.com/24722905/189741614-caf52a37-98a4-47fb-b757-be81c0512844.jpg" width="350px" height="262px" align="right"/>

**MSc Computing Science, University of Alberta** &mdash; Sept. 2019 - Oct. 2022 (Expected)

**BSc Honors Physics, University of Alberta** &mdash; Sept. 2014 - Apr. 2018
<br><br>
<p align="justify">
Welcome! I'm a master's student at the University of Alberta specializing in statistical machine learning (defending Halloween 2022🎃).
  
My background is an undergraduate degree in physics, researching topics such as **ab initio quantum chemistry** and using computation
to test theoretical models of superconductivity before making the short hop over to computing science. I've conducted research in assistive robotics and had the 
incredibly cool experience of implementing a new control scheme on a robotic arm. The focus of my research in graduate school has been
studying optimal sequential decision making, specifically problems that fit under the description of <b>pure exploration in multi-armed bandits</b>. Recently
I've come full circle, working as a research intern at the European Space Agency (ESA) Advanced Concepts Team(ACT), developing **deep learning** models to
identify/predict chaos in dynamical systems as well as identifying dynamical systems from sparse data.
</p>

#### [Simple Regret Minimization in Multi-Armed Bandits](#MAB_SR)
#### [Deep Learning for Dynamical Systems](#DLDS)
#### [Task-Focused Robotic Teleoperation Using Computer Vision](#UVSTO)

## Deep Learning for Dynamical Systems <a name="DLDS"></a>
You can check out a short presentation on my work with the ACT on deep learning for dynamical systems [here](https://docs.google.com/presentation/d/1AdP2ygA-rG8kBoF32PH7BgklXvAzkmm81PfqFgPekKw/edit?usp=sharing), or just check out these cool visualizations.

<table width=90%>
<tr>
<th> Figure 1: Real-time construction of Poincare maps for the <a href="https://en.wikipedia.org/wiki/Swinging_Atwood%27s_machine">Swinging Atwood's Machine (SAM)</a> in a stable (red) and chaotic (green) configuration. On the left is the system configuration, on the right is the Poincare-Map representation of the system.</th>
<th> Figure 2: Sampled Poincare maps for the Swinging Atwood's Machine (colours correspond to trajectories from different initial configurations) for various values of the system mass parameter μ.</th>
</tr>
<tr>
<td width=50%>
<Image src="https://user-images.githubusercontent.com/24722905/189714592-308d97c2-d428-454f-a52a-eb120572404a.gif" width="500" height="238px" /></td>
<td width=50% align="middle">
<Image src="https://user-images.githubusercontent.com/24722905/189714680-f54d6c14-bdc2-428c-a57b-da7816f28378.png" width="400px" height="400px" /></td>
</tr>
</table>

<table width=500px>
<tr>
<th>Figure 3: An example input-output for a deep learning model I developed which estimates the mass ratio parameter of the SAM system which produced the Poincare map (left) input to the network. On the right is the parameter estimate, along with a high-quality Poincare map corresponding to the estimated parameter. </th>
</tr>
<tr>
<td width="500px">
<Image src="https://user-images.githubusercontent.com/24722905/189736428-af463574-c211-495a-80a5-b8302fbd1ac9.png" width="500px" height="250px" />
</td>
</tr>
</table>
