## SET 1- MAKEMORE (PART 1)🔗

Introduced to the concept of a bigram character-level language model and explored its training, sampling, and evaluation processes. Evaluation was performed using the Negative Log Likelihood (NLL) loss to assess the model's quality.

The model was trained in two distinct ways, both yielding identical results:

- **Frequency-Based Approach**: The bigram frequencies were counted and normalized directly.
- **Gradient-Based Optimization**: The counts matrix (the blue table matrix) was optimized using a gradient-based framework, guided by minimizing the NLL loss. \
\
This demonstrated that both methods converge to the same result, highlighting their equivalence in achieving the desired outcome.

-------

**✍🏻Notes:**
Hello. These are my Notes and Codes repo of training my second neural network. This is obviously from the video (Makemore - Part 1) put on this by the main man himself, Andrej Karpathy.   \
\
**You can view my portfolio blog for a detailed description. You can read it [here](https://muzzammil-ai.netlify.app/personal-projects)** \
\
You will find all my notes that I have understood on this in the notes directory. The codes have been broken down into bit-by-bit so that I have a better understanding on them. **I've divided them into 3 sections, so both the notes and the notebooks have the same corresponding names.**

&nbsp;

Follow the codes in order if you are revisiting them. Best way is to start from the notes, as the respective notebooks are linked there itself after the explainations. \
There are some useful comments inside the notebooks as well. So make sure you read those as well :)

-------

*See you in the next one!*