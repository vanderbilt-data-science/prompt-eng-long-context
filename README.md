# Prompt Engineering
Prompt engineering powered by long contexts

# https://bit.ly/long-context

## Background

[Prof. Jules White](https://www.coursera.org/instructor/juleswhite), Director of the Future of Learning and Generative AI Institute, Vanderbilt University

[Prof. Jesse Spencer-Smith](https://www.vanderbilt.edu/datascience/person/jesse-spencer-smith/), Chief Data Scientist and Interim Director, Data Science Institute, Vanderbilty University


![image](https://github.com/vanderbilt-data-science/prompt-eng-long-context/assets/5521243/942ed97c-6020-4fa9-8f0b-5653f18a4eb8)


### Context Length

When working with Large Language Models (LLMs), you often run up against a limit of the length of the conversation. LLMs have a limit to how much of a conversation they can attend to at one time, called the context length. The context length is a function of the model, and models that have long context lengths require significantly more compute power, and are therefore more expensive to use. 

Context length is measured in tokens. Tokens are words, or subwords. Some common words can be represented as one token, whereas less common words (or words from a language not favored in the training of a model) may take two or more tokens to be represented. 

Long context lengths allow for applications that are not possible with models with shorter context lengths. 

### In-Context Learning

To train a model on a new task requires significant compute, on the order of hours, days or more. 

LLMs have the ability to learn without training.

When shown examples of a task being carried out, a LLMs can learn to solve the problem, but that learning only lasts as long as context length. Once you are past the context length, the model loses the ability to solve the problem.

In-context learning occurs on the order of seconds, and requires the same compute as inference--orders of magnitude less than training. In terms of cost, this is pennies versus hundreds of dollars. 

## Negotiation Classification Task

Given a sentence from a negotiation, classify that sentence into one of 19(!) different categories:

Category 1: Asking positional information

Category 2: Providing priority-related information

Category 3: Asking for priority-related information

Category 4: Providing preference-related information

Category 5: Asking for preference-related information

Category 6: Clarification

Category 7: Single-issue activity

Category 8: Multi-issue activity

Category 9: Contentious Communication (Stressing Power, Criticism, Threat, Hostility)

Category 10: Substantiation(Substantiation, Asking for substantiation and Rejecting substantiation)

Category 11: Positive Statements (Positive affective reaction and Positive relationship remarks)

Category 12: Negative Statements (Negative affective reaction and Negative relationship remarks)

Category 13: Providing positional information

Category 14: Procedural comments (Procedural suggestion, Procedural discussion, Time management)

Category 15: Humor

Category 16: Rejecting Offer

Category 17: Accepting Offer

Category 18: Active listening

Category 19: Other

Using traditional methods to train a classification model using an LLM resulted in an accuracy of ~74% and took several days of training. 

Let's see how well we can do using in-context learning.

### Test Set

Examine the [test set](negotiation-testing-prompt) of negotiation statements. Can you determine which category the sentences belong in?

Examine the [test set answers](negotiation-testing-prompt-answers). How did you do?

What could help you do better with the task?

### Training Prompt

Examine the [training prompt](negotiation-training-prompt). Notice that the prompt includes:
- descriptions of each of the categories
- examples of each of the categories.

This is an example of in-context learning. In other iterations, we have simply supplied examples (dozens for each). For GPT4, this type of prompt has worked best. 

Open the Chat Playgound and select GPT4-32.

Paste in the training prompt. It should return a summary of the categories. Give a summary of 19 categories? If not, please raise your hand and share what it returned. If it returned fewer than 19 categories, the learning has failed, you'll want to clear the chat and restart. 

### Testing Prompt

Now that the training prompt has successfully run, the model is ready to apply what it has learned. 

Paste the [test set](negotiation-testing-prompt) into the chat window. 

Did it return 20 sentences? How did it do?

How could we ensure the model is performing well?

### Comparison of Traditional Model Training and In-Context Training

Here is the performance of a model trained in the traditional manner over the span of several days (hours of GPU compute):
![image](https://github.com/vanderbilt-data-science/prompt-eng-long-context/assets/5521243/7e2e97af-19da-43cb-8db2-c076ea6e150d)


Here is the performance of the model trained in the manner we just carried out, using the same prompt:

![image](https://github.com/vanderbilt-data-science/prompt-eng-long-context/assets/5521243/f50f02fd-648c-4a1d-9f6e-f398301ece59)

This model was "trained" in less than one minute, and performance on par with human coders.

### After the run

Clear the chat, and rerun the [test set](negotiation-testing-prompt). 

What happened?

Why did it fail?

Was the model trained when we ran the training prompt earlier? Was any learning saved?

Every time you run the prompt, you are training a new model.

How do you run validation tests?




## Long-form Text Summarization

In the following example, you may use the [provided text](erda-muse-feurzig), or you may choose your own. If you use your own text, be sure the source material is mostly text, and does not exceed ~20K words. 

The provided text is a somewhat dense description of the character of Erda in Wagner's Ring. She is a complex being that seems all-knowing, but can also be confused and unable to function in the world. Ask for a summarization of the passages to get a sense of what Feurzig is conveying.


## Multiple-text Synthesis

At times, I'm reminded of Erda when interacting with ChatGPT, especially when I run out of context (see the [description of this effect](beyond-context-effect)), but I've not successfully mapped out on my own what what the similarities are, and if one informs the other. 

How might we use the long context of GPT4 32K to answer this?

Try the long context to answer other questions synthesizing one or more longer text (so long as the total lenght is less than 32K tokens! You wouldn't want to end up like Erda!)

# Summary

Long-context models provide opportunities for in-context learning and deep analysis that cannot be accomplished with short-context models. 

# Next Steps

Join us at the Data Science Institute and the Future of Learning and Generative AI for upcoming events!

![image](https://github.com/vanderbilt-data-science/prompt-eng-long-context/assets/5521243/1621c348-e590-44dc-967f-ae729b5377e7)


![1](https://github.com/vanderbilt-data-science/prompt-eng-long-context/assets/5521243/48e0eac3-ef63-4e83-8e6d-777d3760d398)
![3](https://github.com/vanderbilt-data-science/prompt-eng-long-context/assets/5521243/081d7d18-9275-4ead-8d2d-5ac2850020fd)
![4](https://github.com/vanderbilt-data-science/prompt-eng-long-context/assets/5521243/1f582587-f99a-45dc-9e90-ee2c7d66525c)


