
#### **NEURAL NETWORKS**
------------
---------
In this we are basically going next-prediction based on characters. So for each letter, we will be providing a large dataset of names of people, and it will be able to generate many more related/fancy names. So right now, it is character level wise, soon we will go words to generate an entire document of text.

&nbsp;

##### **CHAPTER** [00:00:00](https://www.youtube.com/watch?v=PaCmpygFfXo&t=0s) intro
It is a character level language model, therefore we are trying to produce the next character in the sequence.
We are also going to implement a large number of Character Language Models, in terms of the neural networks that are involved in predicting the next character of the sequence: Bigram, Bag of words, MLP, RNN, GRU and Transformer (Some many change as the course progresses).

&nbsp;

##### **CHAPTER** [00:03:03](https://www.youtube.com/watch?v=PaCmpygFfXo&t=183s) reading and exploring the dataset
We have loaded a dataset containing up to 32K names. We are starting with the first Language Model - Bigram. Which basically considers only 2 characters at once: One is the previous character which is there and using that to predict the next one. (It is a weak language model, but is a great place to start).

&nbsp;

##### **CHAPTER** [00:06:24](https://www.youtube.com/watch?v=PaCmpygFfXo&t=384s) exploring the bigrams in the dataset
Check in code file *(A-Main-Notebook)*

&nbsp;

##### **CHAPTER** [00:09:24](https://www.youtube.com/watch?v=PaCmpygFfXo&t=564s) counting bigrams in a python dictionary
Check in code file *(A-Main-Notebook)*

&nbsp;
##### **CHAPTER** [00:12:45](https://www.youtube.com/watch?v=PaCmpygFfXo&t=765s) counting bigrams in a 2D torch tensor ("training the model")
Here we are making a 2D Array where we can see in how many instance the second character will follow the first character.
We have basically created a 2D Array using PyTorch, Instead of that dictionary we manually made. This is a lot cleaner.
Check in code file *(A-Main-Notebook)*

&nbsp;

##### **CHAPTER** [00:18:19](https://www.youtube.com/watch?v=PaCmpygFfXo&t=1099s) visualizing the bigram tensor
Check in code file *(A-Main-Notebook)*

&nbsp;

##### **CHAPTER** [00:20:54](https://www.youtube.com/watch?v=PaCmpygFfXo&t=1254s) deleting spurious (S) and (E) tokens in favor of a single . token
So the graph that was plotted in the above chapter, there are these one additional row and column where the values are for the cases if `<S>` is in the end and if `<E>` is at the beginning, which doesn't make sense because we used them to map the start and end. Instead we will be replacing them with a `.` So in the graph it will be in the corner end `..` as 0. Therefore we also save space.
Check in code file *(A-Main-Notebook)*

&nbsp;

##### **CHAPTER** [00:24:02](https://www.youtube.com/watch?v=PaCmpygFfXo&t=1442s) sampling from the model
Now to perform sampling we are using ['multinomial' from PyTorch](https://pytorch.org/docs/stable/generated/torch.multinomial.html#torch-multinomial), which is like this built-in function which says "You give me distributions and I will give you a sample of integers".
Along with that we are also using ['generator' object from PyTorch](https://pytorch.org/docs/stable/generated/torch.Generator.html#torch.Generator.manual_seed) again to make everything more deterministic - So the values that we get while running the code will remain the same (Won't keep changing)
Finally we saw how a Bigram model performs better than an untrained model in terms of the output produced. Check in code file *(A-Main-Notebook)*

&nbsp;

##### **⭐CHAPTER** [00:36:17](https://www.youtube.com/watch?v=PaCmpygFfXo&t=2177s) efficiency! vectorized normalization of the rows, tensor broadcasting

Note from the author:
	This is an important lecture. As there is one small concept that has been broken down into its most detailed. This also needs to be understood separately and then come back to this video and understand this. 
	**As Andrej said, "This is not to be done fast and loose. So I encourage you to understand, read through, watch tutorials and practice. As we can easily run into major bugs here".**
	Important Timestamps for words of advise:
		**37:15 - 37:40 -> very important advise / hint for next lectures**
		**42:05 -> First intro of broadcasting rules**
		**44:23 - 44:45 -> The "let me scare you a little bit"**
	Links to refer:
		- [PyTorch Documentation on sum() function](https://pytorch.org/docs/stable/generated/torch.sum.html#torch.sum)
		- [The important and to be respected - Broadcasting Semantics](https://pytorch.org/docs/stable/notes/broadcasting.html)

This part was done and the two lines of code which handled this was also executed: `P = N.float()` and `P /= P.sum(1, keepdims=True)`. The second one is where we have used the sum and broadcasting rules.

&nbsp;

##### **CHAPTER** [00:50:14](https://www.youtube.com/watch?v=PaCmpygFfXo&t=3014s) loss function (the negative log likelihood of the data under our model)

So here we are trying to evaluate the performance of our model. First we check the likelihood, which is basically the product of all parameters, but since that won't be very convenient to work with on a large scale (since most of the values are almost close to 0), we take the log likelihood.

Likelihood is the product of all the individual probabilities.
Log Likelihood is the sum of all the log of the individual properties i.e. log(a * b * c) = log(a) + log(b) + log(c)

Now, we usually see how large can the log likelihood value get, to see that we take the Negative Log Likelihood value (we're basically turning the value positive now).
Another practice which is usually followed here, is that we take the overall average of the NLL, rather than the sum. -> This becomes the final considered value, this value represents the quality of our model. The lower it is, the better off we are and the higher it is, the worse off.

&nbsp;

##### **CHAPTER** [01:00:50](https://www.youtube.com/watch?v=PaCmpygFfXo&t=3650s) model smoothing with fake counts

We do model smoothing, where we basically just add values to the list of values (Like adding all values with 1, 5 etc. - More usually means more smoothing. Like adding 10000, so they all more or less get the same count). This is done so that we avoid the possibility of getting an infinite probability.

&nbsp;

------
```embed
title: "NeuralNetworks-LanguageModels-1/A-Main-Notebook.ipynb at main · MuzzammilShah/NeuralNetworks-LanguageModels-1"
image: "https://opengraph.githubassets.com/b86afc9bc61bee3e45c367652c160402d91f2b3adf4ad0294c51d575fe73010f/MuzzammilShah/NeuralNetworks-LanguageModels-1"
description: "[ 4th November, 2024 - PRESENT ]. Contribute to MuzzammilShah/NeuralNetworks-LanguageModels-1 development by creating an account on GitHub."
url: "https://github.com/MuzzammilShah/NeuralNetworks-LanguageModels-1/blob/main/A-Main-Notebook.ipynb"
```
-----
Okay so now, we've trained a respectable, Bigram language model. 

And we saw that: 
- We have both sort of trained that model by looking at the counts of all the bigrams and normalizing the rows, to get probability distributions. 
- We also saw that then we can also then use the parameters of this model to perform sampling of new words (So we sampled new names according to those distributions)
- Finally, we also saw that we can evaluate the quality of this model. And the quality of this model is summarized in a single number, which is the negative log likelihood (nll)
- So, lower the nll number is, the better the model is, because it is giving high probabilities to the actual next characters in all the bigrams in our training set. 

(Contd in [[B-main-makemore-part1]] )