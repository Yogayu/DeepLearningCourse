# Part 1 Introduction

> Can machines think? —— **A. M. Turing**[^1]

### Artificial Intelligence

We are born with human intelligence. When you are a baby, you learn to talk by listening to people around you and learn to walk through hundreds of attempts. When you go to school, you can learn why the earth goes around the sun or how to play the guitar. When you are watching a suspense film, you're trying to figure out who's really responsible based on the clues that you've got. When the New Year comes, you can reflect on the past year and make plans for the next year. As we can see, language, action, learning, reasoning, memory and plan, those are parts of our human intelligence.

For thousands of years, we have tried to understand how human intelligence works and apply it to make intelligent machines. Those machines are able to accomplish more challenging and complex tasks, like play go game, classify the person in photos, identify the spam email, translate between two language, figure out what elements have a great influence on cancer and how to write poems. 

In computer science, we call this intelligence demonstrated by machines Artificial Intelligence. Colloquially, the term "artificial intelligence" is used to describe machines that mimic "cognitive" functions that humans associate with other human minds, such as "learning" and "problem-solving". [WIKI]

### Machine Learning

Machine Learning is a subset of Artificial Intelligence. It is a field of study that gives computers the ability to learn from data without expilicitly being programmed.

Traditional programs algorithm are based on defining rules and logic. If you have some programming experience, you know that programs contain many logic rules and control conditions. For example, you may quickly write programs to determine whether a year is a leap year.

```python
year = 2019
if (year % 4) == 0:
   if (year % 100) == 0:
       if (year % 400) == 0:
           print("YES")
       else:
           print("NO")
   else:
       print("YES")
else:
   print("NO")
```

This is explicitly programmed.



What if we want a computer to identify if there are cats in the picture? How do you tell it by a set of clear, precise rules? An animal with four legs, a tail and fur is a cat? Don't dogs have these characteristics too? It's hard to write those rules. 

Think about another way, instead of writing a bunch of rules, like four legs, a tail, a fur, a meow, and so on. To tell a computer what a cat is, we gave it lots of pictures of cats, and lots of pictures of non-cats. Then, machine learning algorithms can train themselves to find **patterns** in these images to **define** what a cat looks like. Finally, when you give it a new picture, it can tell whether the picture contains a cat or not. This means learning from data without expilicitly being programmed.

### Deep Learning

Deep Learning is a subfield of machine learning concerned with algorithms inspired by the structure and function of the brain called **artificial neural networks**.

Why we using deep learning method instand of other machine learning method? In general, machine learning methods require us to manually extract features from the data and then use the features as input to the model. Hand engineered features are time consuming, brittle and not scalable in practice. While deep learning can automatically features learning at multiple levels of abstraction. Suppose we want to know if you like a song. There is already a lot of data about songs you mark as likes or dislikes. We need to manually extract features, which may include: song name, singer, lyrics, type, length, rhythm, audio numeric matrix, etc. With the method of deep learning, most of those feature extraction processes can be omitted.

![relationship](./img/whatisdp.png)

Image from 6.S191: Introduction to Deep Learning[^3]

In essence, a computer can do noting but compute. At first glance, AI is powerful yet mysterious. You may wonder: How can a machine beat the world's best go player? How can siri understand what you are saying and respond to you?  Why YouTube know which video you want to watch? How can the machine drive itself on the road? How could the data science team help Obama win the presidency? How could those things being possible? After this course, things will become clear to you.

### Exercises

1. What is artificial intelligence?
2. What is machine learning?
3. What is deep learning?
4. What's the relationship of artificial intelligence, machine learning and deep learning?
5. What's the different between the traditional programming and machine learning? 

## Reference

[^1]: https://www.csee.umbc.edu/courses/471/papers/turing.pdf

[2]: Hands-On Machine Learning with Scikit-Learn and TensorFlow

[3]: [6.S191: Introduction to Deep Learning](http://introtodeeplearning.com)