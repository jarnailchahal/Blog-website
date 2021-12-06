---
layout: post
title: Tranversing a Binary tree
subtitle: How to transverse a binary tree using recursion?
cover-img: /assets/img/GBgraph.jpg
tags: [Data Analysis]
---

### Lets say we want to convince upper management of an example company to hire new Helpdesk employee(s).

Consider the following Binary Tree as an example:

![default]('assets/img/d.png') *Default*

As we can see, the provided tree only have 5 nodes. How can we transverse i.e. visit each node of the given tree?

An easy way to do that might be recursion.


```python

1 class TreeNode:
2     def __init__(self, val):
3         self.val = val
4       self.left = None
5       self.right = None
6
7  def inorderTraversal(root):
8     answer = []
9
10    inorderTraversalUtil(root, answer)
11    return answer
12
13 def inorderTraversalUtil(root, answer):
14
15    if root is None:
16        return
17    else:
18        print("1).. before left:",answer)
19        inorderTraversalUtil(root.left, answer)
20        print("2).. after left:",answer)
21        answer.append(root.val)
22        print("3).. before right:",answer)
23        inorderTraversalUtil(root.right, answer)
24        print("4).. after right:",answer)
25        print("---------------")
26        return
27
28 root = TreeNode(1)
29 root.left = TreeNode(2)
30 root.right = TreeNode(3)
31 root.left.left = TreeNode(4)
32 root.left.right = TreeNode(5)
33
34 print(inorderTraversal(root))

```

The above code visits each node of the tree and appends the current node to an answer list. Taking a deeper look, we can see how it does that, We will look at the *interesing* lines of code only:

It starts with line 34 calling inorderTraversal function.
Inside inorderTraversal it creates an empty list called 'answer' at line 8 and then goes into inorderTraversalUtil at line 10.
What happens at this point?


After organizing and modifying parts of the above graph, we should get something similar to the below example. The below graph uses the same data as the one above.

![GoodGraph](https://raw.githubusercontent.com/jarnailchahal/home/master/_site/assets/img/goodgraph.png)*Good Graph*

Here, it is much more clearer that we want the reader(s) to approve hiring of 2 new help-desk analysts [Title] as the gap between Received & Processed tickets is gradually increasing since May [Added Annotation].

#### In conclusion, a good graph should:

*	TELL A VISUAL STORY
*	BE EASY TO UNDERSTAND
* BE TAILORED TO YOUR TARGET AUDIENCE
* BE USER-FRIENDLY
* BE HONEST