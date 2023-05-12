# Symbolic Regression Using Scientific Approaches (SRSci)
 
Automating scientific discovery has been a grand goal dating back to the founders of AI (Herbert Simon et. al. [14, 12, 30]) but remains a holy grail today. The underlying societal impact is immense because of its multiplier effect on applicational domains. 

Symbolic regression discovers an underlying equation that maps from the input to the output of a given dataset. It is one of the best benchmarking tasks for scientific discovery, as it mimics the process of discovering physics laws from experimental data. Over the years, much effort has been made toward symbolic regression, including search-based methods [13, 15], genetic programming [27, 29, 25, 5], reinforcement learning [21, 26, 20, 21], deep function approximation [19, 2, 23, 22, 17, 31, 3, 7, 1], and integrated systems [28, 10, 9, 16]. Most endeavor focuses on horizontal discovery paths, i.e., they directly search for the best equation in the full hypothesis space involving all independent variables (red path in Figure). This path can be challenging because of the exponentially large full hypothesis space.

![example.png](/assets/images/example.png){: style="float: right"}

Interestingly, the widely applied scientific approaches imply vertical discovery paths, which may be more efficient. To discover the ideal gas law $$pV = nRT$$, scientists first held $$n$$ (gas amount) and $$T$$ (temperature) as constants and find $$p$$ (pressure) is inversely proportional to $$V$$ (volume). They then studied the relationship between $$pV$$ and $$n$$, $$T$$. This led to a vertical discovery path (green long dashed path in Figure). The first few steps of a vertical path can be significantly cheaper than the horizontal path because the searches are in reduced spaces involving a small number of independent variables. As a result, the vertical discovery has the potential to supercharge state-of-the-art approaches in modeling complex scientific phenomena with more interlocking contributing factors or processes than what current approaches can handle.


<br/><br/>

This competition calls for **efficient symbolic regressors, which are free to follow vertical (scientific approach motivated), horizontal (machine learning driven), or any new scientific discovery paths**. Essentially, the participants are free to determine what training data is needed to uncover the underlying symbolic expression.

## Design Your Experiments!

In order to discover a symbolic equation $$y=f(X)$$, we will give you an oracle to query. For a minibatch of $$X$$ that you come up with, the oracle will return $$f(X)$$, corrupted by a certain level of noise. $$X$$ is arranged as a matrix, where the $$i$$-th row contains the input $$X_i$$.  $$y$$ should be a vector, where $$y_i$$ denotes the $$i$$-th output. You are allowed to query the oracle as many times as possible within the time limit. 

## Details of the Competition
You will need to submit a Python program for symbolic regression. Unlike most symbolic regression programs, the data needs to be obtained from the oracle described above. The oracle is provided to you via an object of the class Equation_evaluator. Within a given time limit, you are allowed to query the oracle as many times as possible. The way to query the oracle is discussed in [page of how to participate]. 
Your program needs to write the symbolic equation you find into a pre-specified output file. The program is allowed to overwrite the output file as many times as you’d like within the time limit. Only the equation in the last non-overwritten output file will be evaluated.

## Competition Tracks
[Provide a table of time limit, noise type, dataset]

## How to Participate?
[Go to the page of how to participate](/competition-entry/participate/)

## How We will Evaluate?
We will randomly generate a minibatch of input $$X$$, and obtain the ground-truth output $$f(X)$$, and your prediction $$\hat{f}(X)$$. Here $$\hat{f}$$ is the symbolic equation you wrote in the output file. We will report the symbolic equation complexity (measured as the number of nodes in the expression tree), and various loss functions between $$f(X)$$ and $$\hat{f}(X)$$. All the reported values will be the median value across all the equations considered in a single competition track.

Here is the [page](/results/evaluation-criteria/#evaluation-criteria) describing all the loss functions.

Here is the [page] describing our computational environment of evaluation.

## Organizer
- Nan Jiang (Purdue University), jiang631 at purdue dot edu
- Yexiang Xue (Purdue University), yexiang at purdue dot edu


## Discord Contacts

If you want to ask any question, provide some feedback or simply chit-chat, join us at the [Discord server](https://discord.gg/MeGnkHr4).

## References

[1] Steven L. Brunton, Joshua L. Proctor, and J. Nathan Kutz. Discovering governing equations from
data by sparse identification of nonlinear dynamical systems. Proceedings of the National Academy of
Sciences, 113(15):3932–3937, 2016.

[2] Chen Chen, Changtong Luo, and Zonglin Jiang. Elite bases regression: A real-time algorithm for
symbolic regression. In ICNC-FSKD, pages 529–535. IEEE, 2017.

[3] Ricky TQ Chen, Yulia Rubanova, Jesse Bettencourt, and David K Duvenaud. Neural ordinary differ-
ential equations. Advances in neural information processing systems, 31, 2018.

[4] Carla P Gomes, Bart Selman, and John M Gregoire. Artificial intelligence for materials discovery.
MRS Bulletin, 44(7):538–544, 2019.

[5] Baihe He, Qiang Lu, Qingyun Yang, Jake Luo, and Zhiguang Wang. Taylor genetic programming for
symbolic regression. In GECCO, pages 946–954. ACM, 2022.

[6] Qing-Miao Hu and Rui Yang. The endless search for better alloys. Science, 378(6615):26–27, 2022.

[7] John Jumper, Richard Evans, Alexander Pritzel, Tim Green, Michael Figurnov, Olaf Ronneberger,
Kathryn Tunyasuvunakool, Russ Bates, Augustin Žídek, Anna Potapenko, et al. Highly accurate protein
structure prediction with alphafold. Nature, 596(7873):583–589, 2021.

[8] Steve Kelling, Jeff Gerbracht, Daniel Fink, Carl Lagoze, Weng-Keen Wong, Jun Yu, Theodoros
Damoulas, and Carla P. Gomes. ebird: A human/computer learning network for biodiversity con-
servation and research. In Proceedings of the Twenty-Fourth Conference on Innovative Applications
of Artificial Intelligence (IAAI), 2012.

[9] Ross D. King, Jem Rowland, Stephen G. Oliver, Michael Young, Wayne Aubrey, Emma Byrne, Maria
Liakata, Magdalena Markham, Pinar Pir, Larisa N. Soldatova, Andrew Sparkes, Kenneth E. Whelan,
and Amanda Clare. The automation of science. Science, 324(5923):85–89, 2009.

[10] Ross D King, Kenneth E Whelan, Ffion M Jones, Philip GK Reiser, Christopher H Bryant, Stephen H
Muggleton, Douglas B Kell, and Stephen G Oliver. Functional genomic hypothesis generation and
experimentation by a robot scientist. Nature, 427(6971):247–252, 2004.

[11] Heather J Kulik and Pratyush Tiwary. Artificial intelligence in computational materials science. MRS
Bulletin, pages 1–3, 2022.

[12] Deepak Kulkarni and Herbert A Simon. The processes of scientific discovery: The strategy of experi-
mentation. Cognitive science, 12(2):139–175, 1988.

[13] Pat Langley. Data-driven discovery of physical laws. Cognitive Science, 5(1):31–54, 1981.

[14] Patrick W. Langley, Herbert A. Simon, Gary Bradshaw, and Jan M. Zytkow. Scientific Discovery:
Computational Explorations of the Creative Process. The MIT Press, 02 1987.

[15] Douglas B. Lenat. The ubiquity of discovery. Artificial Intelligence, 9(3):257–285, 1977.

[16] C. Lintott, K. Schawinski, A. Slosar, K. Land, S. Bamford, Daniel I. Thomas, M. Raddick, R. Nichol,
A. Szalay, D. Andreescu, P. Murray, and J. V. D. Berg. Galaxy zoo: morphologies derived from visual
inspection of galaxies from the sloan digital sky survey. Monthly Notices of the Royal Astronomical
Society, 389:1179–1189, 2008.

[17] Ziming Liu and Max Tegmark. Machine learning conservation laws from trajectories. Phys. Rev. Lett.,
126:180604, May 2021.

[18] Arun Mannodi-Kanakkithodi and Maria KY Chan. Computational data-driven materials discovery.
Trends in Chemistry, 3(2):79–82, 2021.

[19] Trent McConaghy. Ffx: Fast, scalable, deterministic symbolic regression technology. In Genetic
Programming Theory and Practice IX, pages 235–260. Springer, 2011.

[20] T. Nathan Mundhenk, Mikel Landajuela, Ruben Glatt, Cláudio P. Santiago, Daniel M. Faissol, and
Brenden K. Petersen. Symbolic regression via deep reinforcement learning enhanced genetic program-
ming seeding. In NeurIPS, pages 24912–24923, 2021.

[21] Brenden K. Petersen, Mikel Landajuela, T. Nathan Mundhenk, Cláudio Prata Santiago, Sookyung Kim,
and Joanne Taery Kim. Deep symbolic regression: Recovering mathematical expressions from data
via risk-seeking policy gradients. In ICLR. OpenReview.net, 2021.

[22] M. Raissi, P. Perdikaris, and G.E. Karniadakis. Physics-informed neural networks: A deep learning
framework for solving forward and inverse problems involving nonlinear partial differential equations.
Journal of Computational Physics, 378:686–707, 2019.

[23] Maziar Raissi, Alireza Yazdani, and George Em Karniadakis. Hidden fluid mechanics: Learning ve-
locity and pressure fields from flow visualizations. Science, 367(6481):1026–1030, 2020.

[24] ZY Rao, X Wang, J Zhu, XH Chen, L Wang, JJ Si, YD Wu, and XD Hui. Affordable fecrnimncu high
entropy alloys with excellent comprehensive tensile properties. Intermetallics, 77:23–33, 2016.

[25] Shahab Razavi and Eric R. Gamazon. Neural-network-directed genetic programmer for discovery of
governing equations. CoRR, abs/2203.08808, 2022.

[26] Lara Scavuzzo, Feng Yang Chen, Didier Chételat, Maxime Gasse, Andrea Lodi, Neil Yorke-Smith, and
Karen Aardal. Learning to branch with tree mdps. CoRR, abs/2205.11107, 2022.

[27] Michael Schmidt and Hod Lipson. Distilling free-form natural laws from experimental data. Science,
324(5923):81–85, 2009.

[28] R.E. Valdés-Pérez. Human/computer interactive elucidation of reaction mechanisms: application to
catalyzed hydrogenolysis of ethane. Catalysis Letters, 28:79–87, 1994.

[29] Marco Virgolin, Tanja Alderliesten, and Peter A. N. Bosman. Linear scaling with and within semantic
backpropagation-based genetic programming for symbolic regression. In GECCO, pages 1084–1092.
ACM, 2019.

[30] Hanchen Wang, Tianfan Fu, Yuanqi Du, Wenhao Gao, Kexin Huang, Ziming Liu, Payal Chandak,
Shengchao Liu, Peter Van Katwyk, Andreea Deac, Anima Anandkumar, Karianne Bergen, Carla P.
Gomez, Shirley Ho, Pushmeet Kohli, Joan Lasenby, Jure Leskovec, Tie-Yan Liu, Arjun Manrai, Debora
Marks, Bharath Ramsundar, Le Song, Jimeng Sun, Jian Tang, Petar Velickovic, Max Welling, Connor
Coley, Yoshua Bengio, and Marinka Zitnik. Enabling scientific discovery with artificial intelligence.
Nature, 2022.

[31] Yexiang Xue, Md. Nasim, Maosen Zhang, Cuncai Fan, Xinghang Zhang, and Anter El-Azab. Physics
knowledge discovery via neural differential equation embedding. In ECML/PKDD (5), volume 12979
of Lecture Notes in Computer Science, pages 118–134. Springer, 2021.