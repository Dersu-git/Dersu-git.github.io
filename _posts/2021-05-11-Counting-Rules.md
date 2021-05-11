---
layout: post
title: "Counting Rules"
author: "Dersu"
categories: journal
tags: [documentation,sample]
image: monopoly.jpg
---

This is a note (copy) for Chapter 3 Counting in the book Elementary Probability Theory (Kai Lai Chung, Farid AitSahlia). 

## Why counting?
The sample space is all possible outcomes of an experiment. Each outcome is a sample point. An event is a subset of the sample space.

Classically, the probability of an event $A$ is the ratio of the number of sample points favorable to that event to the total number of sample points in the sample space $\Omega$, provided that all the sample points are equally likely.


$$
P(A)=\frac{|A|}{|\Omega|}=1-\frac{|A^c|}{|\Omega|}
$$

$A^c$ is the complement of $A$.

So to calculte the probability of an event A amounts to counting the sample points both in the subset A and in the sample space, when each sample point happens equally likely.

If an experiment is done step by step, every step has multiple possible outcomes, say $m_1$ possibilities for step 1, $m_2$ for step 2, ..., $m_r$ for step r, then  Fundamental Rule says the number of all possible outcomes, $a$, is the product of all $m_j$. 

$$
a = m_1 \times m_2 \times \cdots \times m_r.
$$

$a$ hints *arrangements*.

For example, there are 3 choices for Appetizer and 4 for Main course and 5 for desserts, we get the number of different dinners $a = 3\times 4 \times 5=60$.

We can model the combinatorial problems in reality with sampling in 4 basic cases. 

A **transparent** urn contains m distinguishable balls marked 1 to m, from which n balls will be drawn under various specified conditions. To count the possile arrangements, i.e. to calculate $a$. 

By "transparent", it means one can see all the balls in the urn during the experiment. Because our purpose is to calculate all the sample points, if it is a black box, we may draw repetitive outcomes that contribute one sample points. Since we are counting, it's confusing, isn't it?

Here the sample space $\Omega$ is ${1,2,\cdots,m}$, each item is a sample point.

## Case I: Sampling with replacement and with ordering
Question: we can interpret a sample with replacement and with ordering to be a n-tuple $(a_1, a_2, \cdots, a_n)$, any $a_i$ is the mark of the ball, namely any number from 1 to m. How many different n-tuples?

Ans: Fundamental Rule works here.

$$
a=m^n.
$$
BTW, to toss a fair coin can be modelled as this case: a urn with 2 distinguishable balls, to draw 1 ball. 

To throw a dice 3 times also can be modelled as this case: a urn with 6 distinguishable balls, to draw 3 balls in order. 

To throw 3 distinguishable dice once is also this case.


## Case II: Sampling without replacement and with ordering

Question: Again, a sample can be denoted by a n-tuple $（a_1, a_2, \cdots, a_n）$ with a restriction that all $a_j$ be different. How many such n-tuples?

Ans: step 1, there are $\binom{m}{1}$ possibilities for $a_1$; step 2, $\binom{m-1}{1}$ for $a_2$;...; step n, $\binom{m-n+1}{1}$ for $a_n$. Hence,

$$
a=m\times (m-1) \times \cdots \times (m-n+1).
$$

Particularly, when n=m, the result is the **permutation** of m distinguishable balls.

$$
a=m\times (m-1) \times \cdots \times 1=m!.
$$
## Case III: Sampling without replacement and without ordering

Question：We are dealing with a set with the size n $\{a_1, a_2, \cdots, a_n\}$, all $a_j $ being different. How many such sets?

Ans: Likewise, step 1, there are $\binom{m}{1}$ possibilities for $a_1$; Step 2, $\binom{m-1}{1}$ for $a_2$;...; step n, $\binom{m-n+1}{1}$ for $a_n$.

But the items in a set are unordered. 

**Each unordered sample of size n produces n! ordered ones.**[1]

For example, if $m=5, n=3$, the subsets $\{2,4,5\}$ can be drawn in 3!=6 ways as follows:

$(2,4,5),(2,5,4),(4,2,5),(4,5,2),(5,2,4),(5,4,2).$  

Hence,

$$
a=\frac{m\times (m-1) \times \cdots \times (m-n+1)}{n!}=\frac{m!}{n!(m-n)!}=\binom{m}{n}.
$$
This is the **combination**, counting how many ways to choose unordered n balls from m different balls。

### Case IIIa: Partition into numbered groups, groups are ordered

Suppose there are $m_1$ balls of color no. 1, $m_2$ balls of color no. 2, ..., $m_r$ balls of color no. r. Their colors are disguishable but balls of the same color are not. $m_1+m_2+\cdots+m_r=m$, how many distinguishable arrangements of these m balls are there?

Question: We are dealing with r-tuples $(\{a_{1,1},\cdots, a_{1,m_1}\}, \{a_{2,1},\cdots, a_{2,m_2}\},\cdots, \{a_{r,1},\cdots, a_{r,m_r}\})$

Ans: Step 1, there are $\binom{m}{m_1}$ for the first group with $m_1$ members; step 2,$\binom{m-m_1}{m_2}$; step 3,$\binom{m-m_1-m_2}{m_3}$; ...; step r, $\binom{m_r}{m_r}$. Hence,


$$
a=\binom{m}{m_1}\binom{m-m_1}{m_2}\cdots \binom{m-m_1-\cdots-m_{r-1}}{m_r}
=\frac{m!}{m_1!m_2!\cdots m_r!}.
$$
For example, if $m_1=m_2=2,m=4$, and the colors are black and white, there are 6 distinguishable arrangements: 

••oo $\space$ •o•o  $\space$   •oo•  $\space$   o•o•  $\space$  o••o $\space$ oo••

Namely, $(\{1,2\},\{3,4\}),(\{1,3\},\{2,4\}),(\{1,4\},\{2,3\})，(\{2,4\},\{1,3\}),(\{2,3\},\{1,4\}), (\{3,4\}，\{1,2\})$.

### Case IIIb：Partition into numbered groups, groups are unordered

Let a population of m objects be subdivided into r groups: $m_1$ into group no.1, $m_2$into group no.1,...,$m_r$  into group no.r, where $m_1+m_2+\cdots+m_r=m$ and all $m_j\geq1$. We are not arranging the numbered groups in order.

Question：we will get a set $\{\{a_{1,1},\cdots, a_{1,m_1}\}, \{a_{2,1},\cdots, a_{2,m_2}\},\cdots, \{a_{r,1},\cdots, a_{r,m_r}\}\}$. 

Ans: Like Case IIIa, step 1, there are $\binom{m}{m_1}$ for the first group with $m_1$ members; step 2,$\binom{m-m_1}{m_2}$; step 3,$\binom{m-m_1-m_2}{m_3}$; ...; step r, $\binom{m_r}{m_r}$. The only difference is the groups are unordered. 

Each unordered sample of size $r$ produces $r!$ ordered ones.

So,

$$
a=\frac{\binom{m}{m_1}\binom{m-m_1}{m_2}\cdots \binom{m_r}{m_r}}{r!}=\frac{m!}{m_1!m_2!\cdots m_r!r!}.
$$
E.g. In how many ways can four people split into two pairs?
$\{\{1,2\},\{3,4\}),(\{1,3\},\{2,4\}),(\{1,4\},\{2,3\}\}$.

This is the correct interpretation if the two pairs are going to play chess or pingpong games and two equally good tables are available to both pairs. 

But now suppose the two pairs are going to play double tennis together and the "first" pair has the choice of side of the court, or will be the first to serve. It will then make a difference whether {1,2} precedes {3,4}, or vice versa. In this scenario, we go back to Case IIIa.

## Case IV: Sampling with replacement and without ordering

Question: The sample can be denoted as $\{a_1, a_2, \cdots, a_n\}$, but different $a_j$ may be the same number, then the size of the set is changing from 1 to n.

For example, 6 indistinguishable dice are rolled. How many different arrangements we will get?

This is confusing. 

Let's look at a simpler example: Toss 2 indistinguishable coins, how many different arrangements？

Brute force will do. If the result is $(T,T)$, it's $\{T, T\}=\{T\}$; $(H,H)$ leads to $\{H, H\}$; $(H,T)$ or $(T,H)$ is recorded as $\{H, T\}$. So, $a=3$.

> This probability should be have something to do with the experimental frequency of the occurrence of the event.[2]

If 2 coins are indistinguishable, are $(H,T)$ and $(T,H)$ one sample point? No. In experiments, each coin is independent. Each coin can be labelled or named in reality. But people can't tell who is who. And they are used in games as indistinguishable, for example, there are 3 dice in Monopoly, 2 white ones look alike, the third is red, the designer doesn't bother to make the 2 white dice indistinguishable for us. How many distinguishable arrangements? Yes, we can count. But from experiment point of view, we are categorizing based on raw experiment outcomes.

Let's solve the question: 6 indistinguishable dice are rolled. How many different arrangements we will get?

Experimentally let's label each dice as they are independent by nature. Say we use 6 dices with red, orange, yellow, green, blue, purple colors. 

We record the result in this color order as a 6-tuple $(a_1, a_2, \cdots, a_6)$ and observe whether there is a patern.

First prepare a "tally sheet" with numbers indicating the balls in the top line.

Say for the first time the dice are rolled, the result is $(2,1,3,4,5,2)$. We put a check mark in the column of number 2, then a check in column 1, ..., finally, a check in column 2. (In fact we can see at a glance there are two 2, and the rest 1, 3, 4, 5.)

1 | 2| 3| 4 |5|6
---|---|---|---|---|---
$\surd$ |$\surd\surd$ |$\surd$|$\surd$|$\surd$|

If the second result happens to be the same tuple $(2,1,3,4,5,2)$, this is not a different possibility, it's ignored.

If the 3rd result is $(1,1,2,2,1,1)$, mark checks in the second line of the sheet. (One can figure out at a glance there are four 1 and two 2.)

1 | 2| 3| 4 |5|6
---|---|---|---|---|---
$\surd$ |$\surd\surd$ |$\surd$|$\surd$|$\surd$|
$\surd\surd\surd\surd$ |$\surd\surd$ ||||

The 4th result is $(1,2,3,4,5,6)$, the 5th one is $(2,1,4,3,6,5)$, from experiments point of view, they are different possibilities. But count in this case, they are categorized as one arrangement (Tuples fall in a set), recorded in line 3. (In experiment, one can tell these two outcomes are the same arrangement intutively.)

1 | 2| 3| 4 |5|6|Patern
---|---|---|---|---|---|---
$\surd$ |$\surd\surd$ |$\surd$|$\surd$|$\surd$||$\surd \mid \surd \surd \mid \surd \mid \surd \mid \surd$
$\surd\surd\surd\surd$ |$\surd\surd$ |||||$\surd\surd\surd\surd \mid  \surd\surd \mid \mid \mid \mid$
$\surd$ |$\surd$ |$\surd$|$\surd$|$\surd$|$\surd$|$\surd \mid \surd \mid \surd \mid \surd \mid \surd \mid \surd$

We can see a patern: 6 check marks are mixed with 5 bar marks. As Case III, it's a question of choosing 6 unordered balls from 11 different balls.

Generally, 
$$
a= \binom{m-1+n}{n}.
$$

Observing all above, the counting rules are the following:

1)Divide the sampling task into independent steps: step 1, step 2,..., step r.

2)Calculate "inside" each step.

3)Examine whether "steps" are ordered practically. Steps means order inherently, the number of arrangement need to be divided by $r!$ if no order is required.

## Examples

**Problem 1**: (Quality Control). Suppose that in a bushel of 550 apples 2% are rotten ones. What is the probability that a "random sample" of 25 apples contains 2 rotten apples?

Ans: $\Omega$={550 apples choose 25}, $A$={25 apples contains 2 rotten apples}, there are $550\times 2\%=11$ rotten apples, and 539 good ones.
$$
|\Omega|=\binom{550}{25} 
$$
Step 1: choose 23 good apples from 539 ones.

Step 2: choose 2 rotton apples from 11 ones.

$$
|A|=\binom{539}{23}\times\binom{11}{2}
$$
Hence,
$$
P(A)=\frac{|A|}{|\Omega|}=\frac{\binom{539}{23}\times\binom{11}{2}}{\binom{550}{25} }
$$

---

**Probem 2**: if a deck of poker cards is thoroughly shuffled, what is the probability that the four aces are found in a row?

Ans: $\Omega$={a deck of poker cards is thoroughly shuffled}, $A$={the four aces are found in a row}. 
$$
|\Omega|=52!
$$

Step 1: let's bundle the 4 aces as 1, so there are 49 positions in the deck. To choose 1 position from 49. Inside the bundle, there are a permutation of 4 aces. $\binom{49}{1}4!$

Step 2: how many arrangements of the rest 48 cards? $48!$
$$
|A|=\binom{49}{1}4!\times48!
$$
Hence,
$$
P(A)=\frac{|A|}{|\Omega|}=\frac{\binom{49}{1}4!\times48!}{52! }
$$

---

**Problem 3**: Fifteen new students are to be evenly distributed among three classes. Suppose that there are 3 whiz-kids among the 15. What is the probability that each class gets one? One class gets them all?

Ans: Let's deal with the first question.

$\Omega$={15 students divided into 3 groups}, $A$={15 students divided into 3 groups, each group has 1 whiz-kid}. 

Assume the groups are ordered.

$$
|\Omega|=\binom{15}{5} \times \binom{10}{5} \times \binom{5}{5} =\frac{15!}{5!5!5!}
$$

Step 1: choose 4 student from 12, and choose 1 whiz-kid from 3. $\binom{12}{4}\binom{3}{1}$

Step 2: choose 4 student from the rest 8, and choose 1 whiz-kid from 2. $\binom{8}{4} \binom{2}{1}$

Step 3: choose 4 student from the rest 4, and choose 1 whiz-kid from 1. $\binom{4}{4} \binom{1}{1}$

$$
|A|=\binom{12}{4}\binom{3}{1} \times \binom{8}{4} \binom{2}{1} \times \binom{4}{4} \binom{1}{1}=\frac{12!}{4!4!4!}3!
$$
Hence,
$$
P(A)=\frac{|A|}{|\Omega|}=\frac{\frac{12!}{4!4!4!}3!}{\frac{15!}{5!5!5!} }
$$
If the groups are unordered.
Then both $|A|$ and $|\Omega|$ need to be divided by $3!$, the $P(A)$ stays the same.

Now the second question: One class gets 3 whiz-kids?

Same $|\Omega|$. Still let's assume the groups are ordered.

Students are labelled as: $(s_1,s_2,\cdots,s_{12},w_1,w_2,w_3)$

3 classes are labelled as 3 types:
 $(\{w_1,w_2,w_3,s_{i1},s_{i2}\},\{s_{i3},s_{i4},\cdots,s_{i7}\},\{s_{i8},\cdots,s_{i12}\})$,

Or $(\{s_{i_1},s_{i_2},\cdots,s_{i_5}\},\{s_{i_6},s_{i_7},w_1,w_2,w_3\},\{s_{i_8},\cdots,s_{i_{12}}\})$,

Or $(\{s_{i_1},s_{i_2},\cdots,s_{i_5}\},\{s_{i_6},s_{i_7},\cdots,s_{i_{10}}\},\{s_{i_{11}},s_{i_{12}},w_1,w_2,w_3\})$.

$i_1,\cdots,i_{12}$ is a rearrangement of $1,2,\cdots,12$.

Step 1: choose 1 of 3 groups to get all whiz-kids. 
$a_1=\binom{3}{1}$

Step 2: if the groups are of the first type, namely, the whiz-kids are in the first group, choose 2 from 12, and choose 5 from 10, and choose 5 from 5
$a_{21}=\binom{12}{2}\binom{10}{5}\binom{5}{5}=\frac{12!}{2!5!5!}$

if the whiz-kids are in the 2nd group, choose 5 from 12, and choose 2 from 7, and choose 5 from 5
$a_{22}=\binom{12}{5}\binom{7}{2}\binom{5}{5}=\frac{12!}{5!2!5!}=a_{21}$

if the whiz-kids are in the 3rd group, choose 5 from 12, and choose 5 from 7, and choose 2 from 2
$a_{23}=\binom{12}{5}\binom{7}{5}\binom{2}{2}=\frac{12!}{5!5!2!}=a_{21}=a_{22}$

$$
|A|=a_{21}+a_{22}+a_{23}=a_1\times a_{21} =3\times \frac{12!}{2!5!5!}
$$
Hence,
$$
P(A)=\frac{|A|}{|\Omega|}=\frac{3\times \frac{12!}{2!5!5!}}{\frac{15!}{5!5!5!} }
$$
Like above, if the groups are unordered, $P(A)$ is the sames.

---

**Problem 4**: Six dice are rolled. What is the probability of getting three pairs?

Ans:$\Omega$={Six dice are rolled}, $A$={three pairs of 6 dices}. 
$$
|\Omega|=6^6
$$
Step 1: Choose 1 pair from 6 dices. This pair might show any number of 6.$a_1=\binom{6}{2}\binom{6}{1}$.

Step 2: Choose 1 pair from the rest 4 dices, this pair might show any number of 5.
$a_2=\binom{4}{2}\binom{5}{1}$.

Step 3: Choose 1 pair from the rest 2 dices, this pair might show any number of 4.
$a_3=\binom{2}{2}\binom{4}{1}$.

Obviously, the pairs are not ordered.
Hence,
$$
|A|=\frac{\binom{6}{2}\binom{6}{1} \times \binom{4}{2}\binom{5}{1}\times  \binom{2}{2}\binom{4}{1}}{3!}=\frac{6!}{2!2!2!}\frac{6\times 5\times 4}{3!}
$$

However, by definition, some sample points in the sample space fall in the event A subset, so we can calculate the probability by counting the number of sample points in the subset A and in the sample space.

We have to think through when we shrink the size of A by categorizing some sample points to be 1, how many sample points originally?

Here, let A' be 3 ordered pairs. Then multiple sample points are not categorized into 1.

$$
|A'|=\binom{6}{2}\binom{6}{1} \times \binom{4}{2}\binom{5}{1}\times  \binom{2}{2}\binom{4}{1}=\frac{6!}{2!2!2!}6\times 5\times 4
$$
Hence,
$$P(A')=\frac{|A'|}{|\Omega|}=\frac{\frac{6!}{2!2!2!}6\times 5\times 4}{6^6}$$



---
Problem 5. (Birthdays). What is the probability that among n people there are at least two who have the same birthday?

Ans: $\Omega$={n people, birthday could be one of 365 days}, $A$={at least two who have the same birthday}. $A^c$={everyone has a unique birthday}

$$
|\Omega|=365^n
$$
Step 1: choose 1 days from 365 for people 1. $a_1=365$

Step 2: choose 1 day from 364 for people 2.$a_2=364$

...

Step n: choose 1 day from 365-n+1 for people n.$a_n=365-n+1$

$$
|A^c|=a_1\times \cdots \times a_n=(365)_n
$$

Hence,
$$
P(A)=1-\frac{|A^c|}{|\Omega|}=1-\frac{(365)_n}{365^n}
$$



#### Reference  
[1]Kai Lai Chung, Farid AitSahlia, Elementary Probability Theory(Fouth Edition), p52  
[2]Kai Lai Chung, Farid AitSahlia, Elementary Probability Theory(Fouth Edition), p28  
