<img src="https://user-images.githubusercontent.com/24722905/189741614-caf52a37-98a4-47fb-b757-be81c0512844.jpg" width="40%" align="right" style="vertical-align:middle;margin:2px 20px"/>

**MSc Computing Science, University of Alberta** &mdash; Sept. 2019 - Oct. 2022 (Expected)

**BSc Honors Physics, University of Alberta** &mdash; Sept. 2014 - Apr. 2018

<a href="https://github.com/connorsteph/connorsteph/files/9551407/stephens_resume_flattened.pdf">Resume</a>
<br>
<a href="https://github.com/connorsteph/connorsteph/files/9551407/stephens_resume_flattened.pdf">CV</a>
<br>
<p align="justify">
Welcome! I'm a master's student at the University of Alberta specializing in statistical machine learning (defending Halloween 2022🧛).
  
My background is an undergraduate degree in physics where conducted research in topics such as **ab initio quantum chemistry** and using computation
to test theoretical models of superconductivity before making the short hop over to computing science after my degree. I've conducted research in assistive robotics and had the incredibly cool experience of implementing a new control scheme on a robotic arm. The focus of my master's research has been studying algorithms and theory for optimal sequential decision making, specifically for problems that fit under the description of <b>pure exploration in multi-armed bandits</b>. Recently I've come full circle and put my physics background to use, working as a research intern at the European Space Agency (ESA) Advanced Concepts Team(ACT), developing **deep learning** models to identify/predict chaos in dynamical systems as well as identifying dynamical systems from sparse data.
</p>

#### [Simple Regret Minimization in Multi-Armed Bandits](#MAB_SR)
#### [Deep Learning for Dynamical Systems](#DLDS)
#### [Task-Focused Robotic Teleoperation Using Computer Vision](#UVSTO)

## Deep Learning for Dynamical Systems <a name="DLDS"></a>
You can check out a short presentation on my work with the ACT on deep learning for dynamical systems [here](https://docs.google.com/presentation/d/1AdP2ygA-rG8kBoF32PH7BgklXvAzkmm81PfqFgPekKw/edit?usp=sharing), or just check out these cool figures below.

<table width=90%>
<tr>
  <th align="left"> Figure 1: Real-time construction of <a href="https://en.wikipedia.org/wiki/Poincar%C3%A9_map">Poincare maps</a> for the <a href="https://en.wikipedia.org/wiki/Swinging_Atwood%27s_machine">Swinging Atwood's Machine (SAM)</a> in a stable (red) and chaotic (green) configuration. On the left is the system configuration, on the right is the Poincare-Map representation of the system.</th>
<th align="left"> Figure 2: Sampled Poincare maps for the Swinging Atwood's Machine (colours correspond to trajectories from different initial configurations) for various values of the system's mass-ratio parameter, μ.</th>
</tr>
<tr>
<td width=50%>
<Image src="https://user-images.githubusercontent.com/24722905/189714592-308d97c2-d428-454f-a52a-eb120572404a.gif" max-width="500px" /></td>
<td width=50% align="middle">
<Image src="https://user-images.githubusercontent.com/24722905/189714680-f54d6c14-bdc2-428c-a57b-da7816f28378.png" max-width="400px" /></td>
</tr>
</table>

<table width=50%>
<tr>
<th align="left">Figure 3: An example input-output for a deep learning model I developed which estimates the mass ratio parameter of the SAM system which produced the Poincare map (left) input to the network. On the right is the parameter estimate, along with a higher quality Poincare map corresponding to the estimated parameter. </th>
</tr>
<tr>
<td width="50%">
<Image src="https://user-images.githubusercontent.com/24722905/189736428-af463574-c211-495a-80a5-b8302fbd1ac9.png" max-width="500px" />
</td>
</tr>
</table>

<table width=90%>
<tr>
<th align="left"> Figure 4: Pixel-wise classification of the chaoticity of trajectories using a deep learning model with a semantic segmentation approach. Left: ground truth, right: predictions. Note the blob-like artifacts in the prediction (right) which imply multiple classifications for the same trajectory.</th>
<th align="left"> Figure 5: Trajectory chaos classifications obtained from a physics-based deep learning model, making classifications at the trajectory level.</th>
</tr>
<tr>
<td width=50%>
<Image src="https://user-images.githubusercontent.com/24722905/189750499-f61a6b5d-9df4-42bc-8817-4e57d4de1631.png" max-width="500px" /></td>
<td width=50% align="middle">
<Image src="https://user-images.githubusercontent.com/24722905/189750494-3c81dfb9-df0d-4c5e-9897-942c32cb349b.png" max-width="400px" /></td>
</tr>
</table>



## Task-Focused Robotic Teleoperation Using Computer Vision<a name="UVSTO"></a>
[Paper](https://github.com/connorsteph/connorsteph/files/9551660/uvs_teleoperation.pdf) (unpublished)

In the summer of 2018 I led the development of a new method for joystick operation of a robotic arm for reaching and grasping tasks. A general purpose robotic arm typically has around seven degrees of freedom (DOF), corresponding to the possible configuration for all of the joints, e.g. the elbow wrist and shoulder joints. In many applications of robotic arms to assistive living users command motion of the arm using a joystick control. Mapping joystick controls to full specification of the arm's position requires switching between control modes e.g. controlling either the position of the end effector or its orientation. Reaching and grasping objects with a robotic arm can be a slow and mentally taxing task for end users who require assistance carrying out their daily tasks. Some proposed solutions include combining computer vision with automated controllers that enable users to specify an object they wish to grasp. A disadvantage of these systems (other than their complexity) is that many users of assistive robotic value the a user-in-the-loop system in which they retain at least partial control of the arm.

Our proposed solution consisted of a scheme in which a user highlights the object that they wish to grasp on a computer screen, and then use a joystick controller to execute the task. Having the users target marked on a computer allows us to design a joystick control scheme which is defined with respect to their goal. 

