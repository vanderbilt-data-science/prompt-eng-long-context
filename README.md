# prompt-eng-long-context
Prompt engineering powered by long contexts

# https://bit.ly/long-context

## Background

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

Examine the [test set](negotiation-testing-prompt) of negotiation statements. 

## Long-form Text Summarization

In the following example, you may use the provided text, or may choose your own. If you use your own text, be sure the source material is text-heavy, and does not exceed ~20K words. 

## Multiple-text Synthesis


