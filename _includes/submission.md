



Participants were asked to adapt and submit their symbolic regression algorithms to SciBench.
These methods were automatically tested for the the competition.



## Submission Site

To participate of the competition, each member of the team must submit their proposed algorithms. The first member to enroll will create a team name and the other members will choose their team from the list of choices. After enrolling, you are good to go!

[SciBench 2023 on Easychair](https://easychair.org/cfp/content.cgi?a=30862459;draft=1)

## Submission Requirements

For the convenience of evaluting each of the algorithms, we need to enforce the following requirements about the directory so that we can sucessfully run your algorthm. 

1. You need to compress your code impelemntion into a **zip** file with **`YOUR_ALGOITHM_NAME.zip`**.

2. Inside your zip file, specify the extra packages and exact versions in **requirements.txt**, which are required to be installed before running your algorithms.

3. Inside your zip folder, the directory should contains **main.py** function, which is the default file to call your proposed algorithm. Here this the sample directory:
```bash
YOUR_ALGOITHM_NAME/
    main.py
    requirements.txt
    EXTRA_FILES...
    ...
```
4. Your `main.py` needs to takes the following input arguments:
```bash
--eq_name PATH_TO_THE_INPUT_SYMBOLIC_EQUATION \
--noise_type uniform \ # noise type
--noise_rate 0.01 \ # noise rate
--results ../PATH_TO_THE_OUTPUT_FILE.txt \ # save your best predicted expressions into this file
```
The format of `PATH_TO_THE_INPUT_SYMBOLIC_EQUATION` can be found at [Input file format]() and `PATH_TO_THE_OUTPUT_FILE.txt` is detailed in [Output file format]().


