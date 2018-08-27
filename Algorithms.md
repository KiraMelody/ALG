#CS5112: Algorithms and Data Structures for Applications

### **Course Description**

An introduction to some fundamental algorithms and data structures used in current applications. Cryptocurrencies (hashing, Merkle trees, proofs of work), AI (nearest neighbor methods, k-d trees, autoencoders), and VR/AR (gradient descent, least squares, line-drawing algorithms). Lectures will be supplemented with occasional applied clinics taught in the evening. Programming assignments in Python.

### **Course Staff**

Instructors: Ramin Zabih and Greg Zecchini

TA: Richard S. Bowen

Graders/consultants: TBA

### **Course Requirements and Grading**

- **Grade Breakdown:**  Your grade will be determined by the assignments (30%), one prelim (25%), a final exam (35%), and quizzes (10%).

- **Homework:** There will be approximately six short programming assignments. Each assignment will have a due date for completion.

- **Late Policy:** Each student has a total of  **one**  slip day that may be used without penalty for homework. We will also drop your lowest quiz score.

- **Collaboration:** You are required to work in groups of 2 students on each assignment. Please indicate the name of your collaborator at the top of each assignment and cite any references you used (including articles, books, code, websites, and personal communications). If you&#39;re not sure whether to cite a source, err on the side of caution and cite it. You may submit just one writeup for the group. Remember not to plagiarize: all solutions must be written by members of the group. If you are the odd person out we will have you join an existing group of 2.

- **Quizzes:** There will be short multiple-choice quizzes, generally at the end of the week. These are take home, and due within 24 hours.

- **Prelim: In class, on Thursday October 25.** The exam is closed book.

- **Final Exam: In class, on Tuesday December 4.**  The exam is closed book.



Image editing & pirate grammar

Greddy Algorithms are widely used

- SGD for neural networks

Dynamic programming

------

## The shortest path problem

application:

- Make fake photographs
- Speech recognition: DTW
- Pirate grammar

Given an image, how do you cut your an object from it?

**Intelligent scissors** - SIGGRAPH 1995

Idea: Shortest path

**Dynamic Time Warping(DTW)**

### Pirate grammar

Question: what sentence is a pirate most likely to say?

And a sourse and sink, with probability 1

Maximize the product of edge probabilities -> minimize the sum of edge weights

$log\prod_ip_i = \sum_ilogp_i,  0 < p_i \le 1 \rightarrow  logp_i \le0$

### Key property

Consider s-v-t paths, only need to think about s-v, v-t

Fringe node: what you don't have, but can reach by adding one edge(adjacent to an expolored node)

Steps:

1. Foe each $u \in S$ hode the shortest path from s to u, write as d(u)

2. Add an unexpore node v to S, which v is the cheapest in all fringe nodes

   - The fringe node v can be adjactent to several nodes in S
   - 

3. d(v) = min(d(u)+e(u,v))

   $\pi(v)$ shortest path length

4. Remove v from Q to S

Naive Dijkstra with n nodes and m edges is O(mn)

Priority queue implements in O(nlogm)

###Trellis graph

3 node: A/S/H, there are edges with transition probabilities

**Hidden Markov Model**

With S states and T time there are O(ST) nodes in the graph and O(S^2T) edges

Running time is O(S^3T^2)

**Viterbi** only O(S^2T) with dynamic programming

