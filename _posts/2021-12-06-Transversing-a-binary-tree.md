---
layout: post
title: Tranversing a Binary tree
subtitle: How to transverse a binary tree using recursion?
cover-img: /assets/img/GBgraph.jpg
tags: [Data Analysis]
---

### Lets say we want to convince upper management of an example company to hire new Helpdesk employee(s).

Consider the following Binary Tree as an example:

![default](./assets/img/d.png) *Default*

As we can see, the provided tree only have 5 nodes. How can we transverse i.e. visit each node of the given tree?

An easy way to do that might be recursion.


```python

class TreeNode:
    def __init__(self, val):
        self.val = val
        self.left = None
        self.right = None

def inorderTraversal(root):
    answer = []

    inorderTraversalUtil(root, answer)
    return answer

def inorderTraversalUtil(root, answer):

    if root is None:
        return
    else:
        print("1).. before left:",answer)
        inorderTraversalUtil(root.left, answer)
        print("2).. after left:",answer)
        answer.append(root.val)
        print("3).. before right:",answer)
        inorderTraversalUtil(root.right, answer)
        print("4).. after right:",answer)
        print("---------------")
        return

root = TreeNode(1)
root.left = TreeNode(2)
root.right = TreeNode(3)
root.left.left = TreeNode(4)
root.left.right = TreeNode(5)

print(inorderTraversal(root))

```

The above code visits each node of the tree and appends the current node to an answer list.

Taking a deeper look, we can see how it does that:

It starts with



After organizing and modifying parts of the above graph, we should get something similar to the below example. The below graph uses the same data as the one above.

![GoodGraph](https://raw.githubusercontent.com/jarnailchahal/home/master/_site/assets/img/goodgraph.png)*Good Graph*

Here, it is much more clearer that we want the reader(s) to approve hiring of 2 new help-desk analysts [Title] as the gap between Received & Processed tickets is gradually increasing since May [Added Annotation].

#### In conclusion, a good graph should:

*	TELL A VISUAL STORY
*	BE EASY TO UNDERSTAND
* BE TAILORED TO YOUR TARGET AUDIENCE
* BE USER-FRIENDLY
* BE HONEST
