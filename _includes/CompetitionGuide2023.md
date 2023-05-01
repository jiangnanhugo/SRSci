# Symbolic Regression Competition - 2023

tl;dr the first edition of the symbolic regression competition will allow the participants to experiment with their own pipeline to submit the best symbolic regression model. We will have two tracks: best accuracy-simplicity trade-off. Read below for more details and don’t forget to join our Discord server at [https://discord.gg/MeGnkHr4](https://discord.gg/MeGnkHr4).

The participation link is now online! See [Entries](#entries).

# Call for participation

<!-- The 2023 edition of the Symbolic Regression (SR) competition will be composed of two tracks: performance track and interpretability track.  -->
The participants will have the freedom to apply their own pipeline with the objective of returning symbolic models that best describe the data. 
The models will be evaluated according to accuracy and simplicity.

The competition will start 01-May-2023 and last 3 months. The participants will gain access to 10 synthetic symbolic equations.
During the three months, the participants can apply an SR approach or pipeline of their choice, e.g., their own novel algorithm or an existing SR package, as well as pre- and post-processing methods (e.g., feature construction and model simplification, respectively) to find suitable symbolic models for the corresponding data sets. 

Enrollment will be done via GitHub Classroom, at a link to be announced soon. 
This will result in a private repository that can be accessed only by the participating team and the organizers.  
The repository contains detailed submission instructions, a default directory structure, and the data sets for the two tracks.

# Track - Performance

The participants will be free to experiment with these data sets until the deadline. 
Analysis on each dataset should include the production of a single best model for each dataset, and an extended abstract discussing the pipeline.

At the competition submission deadline the repository of a participating team should contain:

- [required] A file containing a single model as a **sympy-compatible expression**, selected as the best expression for that data set, named `dataset_X_best_model`.
- [required] A maximum 4 page extended abstract in PDF format describing the algorithm and pipeline. This PDF must contain the name and contact information of the participants.
- [to be eligible for prize] Reproducibility documentation in the `src` folder.
    - Installation and execution instructions 
    - Scripts (Jupyter Notebook is accepted) with detailed instructions of all steps used to produce models (including hyperparameters search, if any) 

## Evaluation criteria

We have two leadboards: public and privaite.

### Public Leadboard

### Private Leadboard


The final score of each competitor will be composed of:

- *acc*: Rank based on the accuracy (R^2) on a separate validation set for each data set.
- *simpl*: Rank based on the a simplicity (number of nodes calculating by traversing the sympy expression) of the model for each data set.

The rank will be calculated for each data set independently such that, with N participants, the k-th ranked competitor (k=1 being the best) will be assigned a value of *N - k + 1*. The final score will be the harmonic mean of all of the scores and each participant will be ranked accordingly:

$$
score = \frac{2*n}{ \sum_{i=1}^n (1/acc[i]) + (1/simpl[i]) for i in (1..n)]}
$$

# Come chat with us!!

If you want to ask any question, provide some feedback or simply chit-chat, join us at the Discord server: [https://discord.gg/MeGnkHr4](https://discord.gg/MeGnkHr4).

# Entries

To participate of the competition, each member of the team must submit their proposed algorithms with the link corresponding to the desired track. The first member to enroll will create a team name and the other members will choose their team from the list of choices. After enrolling, you are good to go!

Track 1: [https://easychair.org/cfp/content.cgi?a=30862459;draft=1](https://easychair.org/cfp/content.cgi?a=30862459;draft=1)


# Organizers

<a href="https://www.cs.purdue.edu/homes/yexiang/" ><img style="float:center;height:100px;" src="https://www.cs.purdue.edu/homes/yexiang/images/emily2019/YexiangXue.jpg"></a>

Yexiang Xue - Purdue University, USA - yexiang (at) purdue.edu

Yexiang is an associated professor in the Department of Computer Science at Purdue University, USA. His research focuses on developing intelligent systems that tightly integrate decision making with machine learning and probabilistic reasoning under uncertainty. He has made core contributions across multiple scientific domains, ranging from artificial intelligence, machine learning, renewable energy, materials science, crowdsourcing, citizen science, urban computing, ecology, to behavioral econometrics. In his research, he focuses on developing cross-cutting computational methods with applications to a variety of domains, with an emphasis in the new exciting area of computational sustainability and scientific discovery. Prior to coming to Purdue, he received my Ph.D. degree in the Department of Computer Science at Cornell University, working with Professor Carla Gomes and Professor Bart Selman. He received a B.Sc. in 2011 from School of EECS, Peking University, China.

<a href="https://www.cs.purdue.edu/people/graduate-students/jiang631.html" ><img style="float:center;height:100px;" src="https://jiangnanhugo.github.io/images/head.jpg"></a>

Nan Jiang - Purdue University, USA - jiang631 (at) purdue.edu

Nan Jiang is a PhD student in the Department of Computer Science at Purdue University, USA. He is interested in integrating constarint reasoning and probabilistic reasoning algorithms for machine learning.



