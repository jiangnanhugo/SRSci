# Welcome to SciBench 2023 Competitions!

Symbolic regression is the task of finding the underlying symbolic expression from the given dataset. 
The major difficulties of existing symbolic regression benchmarks are that:
- the input data (experiment trials) is generated from random **i.i.d.** distribution.
- the learning algorithm fits to the same dataset during training.

Instead, from the history of experimental physics and experimental chemistry, 
- the data are not necessary **i.i.d.** distributed.
- the datasets are actively queried throughout the process of learning. 


Therefore, we propose a new evaluation paradigm --- Scientist-in-the-loop benchmark for symbolic regression (**SciBench**) that simulates an integrated framework of scientist-in-the-loop for data generation and a learning algorithm for symbolic expression discovery. The goal of this challenge is to explore various approaches to querying data and fitting the model to the dataset. The learning algorithms can determine what training data is needed to uncover the underlying symbolic expression.




## Organizer
- Nan Jiang (Purdue University), jiang631 at purdue dot edu
- Yexiang Xue (Purdue University), yexiang at purdue dot edu


## Discord Contacts

If you want to ask any question, provide some feedback or simply chit-chat, join us at the [Discord server](https://discord.gg/MeGnkHr4).


