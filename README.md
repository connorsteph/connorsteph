<img src="https://user-images.githubusercontent.com/24722905/189741614-caf52a37-98a4-47fb-b757-be81c0512844.jpg" width="40%" align="right" style="vertical-align:middle;margin:2px 20px"/>

**MSc Computing Science, University of Alberta** &mdash; Sept. 2019 - Oct. 2022 (Expected)

**BSc Honors Physics, University of Alberta** &mdash; Sept. 2014 - Apr. 2018

<a href="https://github.com/connorsteph/connorsteph/files/9552451/stephens_resume_flattened.pdf">Resume</a>
<br>
<a href="https://github.com/connorsteph/connorsteph/files/9551407/stephens_resume_flattened.pdf">CV</a>
<br>
<p align="justify">
Welcome! I'm a master's student at the University of Alberta specializing in statistical machine learning (defending Halloween 2022🧛).
  
My background is an undergraduate degree in physics in which I conducted research in topics such as **ab initio quantum chemistry** and using computational methods
to test theoretical models of superconductivity before making the short hop over to computing science after my degree. I've had the opportunity to perform research in assistive robotics and had the incredibly cool experience of implementing a new control scheme on a robotic arm. The focus of my master's research has been studying algorithms and theory for optimal sequential decision making, specifically for problems that fit under the description of <b>pure exploration in multi-armed bandits</b>. Recently I've come full circle and put my physics background to use, working as a research intern at the European Space Agency (ESA) Advanced Concepts Team (ACT), developing **deep learning** models to identify/predict chaos in dynamical systems as well as identifying dynamical systems from sparse data.
</p>
<br>
Here are some things that I've worked on:

#### [Pure Exploration Problems in Bandits](#MAB_PE)
#### [Deep Learning for Dynamical Systems](#DLDS)
#### [Task-Focused Robotic Teleoperation Using Computer Vision](#UVSTO)
#### [Using Quantum Chemistry to Estimate Properties of Exotic Molecules](#PsH)
<br><br><br><br><br><br>

## Pure Exploration Problems in Bandits <a name="MAB_PE"></a>
Paper under double-blind review 
### Motivation
Imagine that your friend has just started a small online clothing store which sells elaborately embroidered sweaters. Setting up production for a new sweater design is a time and labour intensive process, involving designing the new embroidery pattern, setting up the sewing equipment to stitch the pattern, and obtaining the material required for the design. Due to the small-scale nature of their business and the limited amount of sweaters that they can produce each day they plan to maximize their return on initial production set-up time and cost by making a large batch of one design at a time.

Your friend has a several sweater designs that they are considering for production and wants to determine which sweater will be the most popular and sell the most sweaters. In order to make this selection they pay to have a questionnaire-style advertisement hosted on websites: the ad shows users one of the sweater designs, and asks them to rate their interest in buying the sweater from on a scale from 1-3. They are charged a small fee by the ad-hosting service each time a mini-questionnaire is completed and in order to keep costs within their budget has payed the ad service for 500 responses, after which they'll commit to sweater based on the results of the questionnaires. To paraphrase the situation: your friend wants to use a fixed number of noisy samples to make a sweater selection that maximizes some statistic of the number of sweaters sold. For example, they could look to maximize the expected number of sweaters sold, or the probability that they end up selecting the most popular sweater.

If your friend was in charge of the way that users are assigned the sweater that they'll see on their questionnaire they may choose a traditional A/B/n testing approach which would be to show each user a sweater selected uniformly at random. A disadvantage of this approach is that if some of the sweaters designs are truly far more popular than others then this may be the most efficient use of their sampling budget; a more powerful approach would be for them to take a sequential decision making approach to collecting information, for instance ruling out designs that users have already indicated are clearly unpopular and in doing so reserving more samples to rank the popularities of the remaining designs.

This example has several characteristics which are archetypical of pure exploration problems in multi-armed:
* A selection among a finite collection of options has to be made based on stochastic feedback about the quality of each individual option.
* In the absence of additional problem structure we only receive feedback about the option that we chose (e.g. unless we have a way to relate sweaters 1 and 2, asking users about sweater tells us nothing about the quality of sweater 2)  
*The quality of each option is assumed to be fixed during the sampling process (e.g. we assume that fashion trends will not change during the time-span of our user survey), and each sample of this quality is assumed to be independent and identically distributed (i.i.d.).
* Samples can be collected in a fully adaptive fashion; the decision of which sweater to observe a user sample from next can be decided based on all previous observations, and in relevant scenarios the decision to stop sampling can also be made in a data-dependent manner.
* Apart from sampling budget constraints and considerations of sample efficiency there is no `cost' for taking a sample.

---

Pure exploration research is focused on developing and analysing algorithms which select which data to collect along with which option to recommend in order to return the best selection possible. There are many problem settings within this field (such as minimizing the samples required for a learner to be able guarantee a decision of a prescribed quality, or optimizing the quality of a decision given a fixed budget) as well as many measures of the quality of the selection returned. Alas all problem settings and objectives are not made equal in the eyes of a statistician running an experiment in a given real world situation. My thesis goes over state of the art results in many of the pure exploration settings, discussing their strengths and limitations. It also discusses work currently under double-blind review, so stay tuned.

<br><br><br><br><br><br><br><br>

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
<br><br><br><br>

## Task-Focused Robotic Teleoperation Using Computer Vision<a name="UVSTO"></a>
[Paper](https://github.com/connorsteph/connorsteph/files/9551660/uvs_teleoperation.pdf) (unpublished)

In the summer of 2018 I led the development of a new method for joystick operation of a robotic arm for reaching and grasping tasks. A general purpose robotic arm typically has around seven degrees of freedom (DOF), corresponding to the possible configuration for all of the joints, e.g. the elbow wrist and shoulder joints. In many applications of robotic arms to assistive living users command motion of the arm using a joystick control. Mapping joystick controls to full specification of the arm's position requires switching between control modes e.g. controlling either the position of the end effector or its orientation. Reaching and grasping objects with a robotic arm can be a slow and mentally taxing task for end users who require assistance carrying out their daily tasks. Some proposed solutions include combining computer vision with automated controllers that enable users to specify an object they wish to grasp. A disadvantage of these systems (other than their complexity) is that many users of assistive robotic value the a user-in-the-loop system in which they retain at least partial control of the arm.

Our proposed solution consisted of a scheme in which a user highlights the object that they wish to grasp on a computer screen, and then use a joystick controller to execute the task. Having the users target marked on a computer allows us to design a joystick control scheme which is defined with respect to their goal. The idea behind our control scheme was to separate reaching and grasping into two separate modes. In the reaching mode the user can choose to move directly toward or away from the object with one button (guided by a computer vision control scheme) or to provide perturbations in a direction perpendicular to the direction of the object. Figure 5 shows a direct and a perturbed trajectory for comparison.
<table width=90%>
<tr>
<th align="left"> Figure 5: (Left) A direct reaching trajectory guided by first-derivative estimates of the direction to the target. (Right) A reaching path with user perturbations causing the arm to approach from above the direct path to the object.</th>
<th align="left"> Figure 6: (Left) Rotation about the x-axis around the object while in grasping mode. (Right) Rotation about the y-axis while in grasping mode.</th>
</tr>
<tr>
<td width=50%>
<Image src="https://user-images.githubusercontent.com/24722905/189761478-4b665875-453e-4708-88ed-b9105608fcd0.png" width="100%" /></td>
<td width=50%>
<Image src="https://user-images.githubusercontent.com/24722905/189764007-34958c7f-4af5-4cb1-95b9-eb00fce459ab.png" width="100%">
</tr>
</table>

In the grasping mode we imagine that there is a ball which surrounds the object we wish to grasp, and we design our control scheme so that the robot end-effector is always on the surface of the ball, palm pointed to the object. The user can shrink the ball, or move the arm to a different position on the ball. The video below illustrates the idea. Imagine that there is a ball with the object at its center. 
<video src="https://user-images.githubusercontent.com/24722905/189757526-a76145e9-eb21-444f-abe9-8716ed33714f.mp4" width="320" height="240" />
  
<br><br><br><br><br><br><br><br>

## Using Quantum Chemistry to Estimate Properties of Exotic Molecules  <a name="PsH"></a>
  <a href="https://arxiv.org/abs/2208.07907"> Positronium hydride decay into proton, electron, and one or zero photons</a> (submitted to Phys. Rev. Letters A in 2022, &ndash; under review)
  
In the summer of 2016 I worked with another student under the supervision of Prof. Andrzej Czarnecki to calculate the properties of <a href="https://en.wikipedia.org/wiki/Positronium_hydride"> Positronium Hydride </a> (PsH), an exotic molecule which is believed to have been observed in experiments in the 1990s [[1](#1), [2](#2)], however due to its low (theorized) binding energy this molecule has been challenging to study experimentally. In order to estimate the properties of this molecule we made use of numerical optimization along with the <a href="https://en.wikipedia.org/wiki/Variational_method_(quantum_mechanics)"> variational method </a> the approximate the ground state wave function for PsH. In lay man's terms (or at least a lay man with an undergraduate course in quantum mechanics under their belt) the variational method states that the true ground state wavefunction of a system is the unique wavefunction which minimizes the energy functional of the system. In other words if you plug in the wrong wave function and calculate the ground state energy of the system you will get a number which is larger than the true ground state energy. In order to better approximate the true ground state wave function we can parameterize our trial wave functional and use of numerical optimization to optimize the trial parameters to find a wave function which minimizes the energy functional. 

The description above may seem to make these kinds of problems seem trivial. One of the first problems which emerges is that in order to be able to calculate properties of a given trial wave function such as its energy, which is required for the variational method, along with other properties of interest such as the average distance between the positron from the proton and its electron in PsH we need to evaluate potentially complex integrals. In this work we made use of a gaussian wave-function basis which allowed us to analytically evaluate integrals, reducing the problem to one of optimizing the resulting function of trial wavefunction parameters. A possible disadvantage to this approach is that there we cannot guarantee (and in fact it is almost certainly false) that the true ground state wavefunction lies in the space of functions which our parametrization can represent. This presents us with a tradeoff. If we introduce more parameters into our wavefunction then we can potentially reach lower energies (and better approximations to the true ground state wavefunction) at the cost of a more expensive and challenging optimization problem. If we choose a more flexible function approximation scheme we may be able to even further improve our best-case approximation, but we may not be able to analytically calculate expectations of the wave function anymore in additional to the optimization problem. Tackling these problems is a focus for modern quantum chemistry and a promising application of deep learning.

#### References  
[1] R. Pareja, R. M. de la Cruz, M. A. Pedrosa, R. Gonz ́alez, and Y. Chen, Positronium hydride in hydrogen-laden
thermochemically reduced MgO single crystals, Phys. Rev. B 41, 6220–6226 (1990).<a name="1"></a>
  
[2] D. M. Schrader, F. M. Jacobsen, N.-P. Frandsen, and U. Mikkelsen, Formation of positronium hydride, Phys.
Rev. Lett. 69, 57–60 (1992)<a name="2"></a>
