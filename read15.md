# Trees
In this tutorial, we’ll be covering Binary Trees and Binary Search Trees. We will review some common terminology that is shared amongst all of the trees and then dive into specifics of the different types.
## Common Terminology
- Node - A node is the individual item/data that makes up the data structure
- Root - The root is the first/top Node in the tree
- Left Child - The node that is positioned to the left of a root or node
- Right Child - The node that is positioned to the right of a root or node
- Edge - The edge in a tree is the link between a parent and child node
- Leaf - A leaf is a node that does not contain any children
- Height - The height of a tree is determined by the number of edges from the root to the bottommost node
## Sample Tree
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)
## Traversals
An important aspect of trees is how to traverse them. Traversing a tree allows us to search for a node, print out the contents of a tree, and much more! There are two categories of traversals when it comes to trees:
- Depth First
- Breadth First

## Depth First
Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the **root**. Here are three methods for depth first traversal:

- Pre-order:` root >> left >> right`
- In-order: `left >> root >> right`
- Post-order:` left >> right >> root`

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/tree-example.png)

Given the sample tree above, our traversals would result in different paths:

Pre-order: `A, B, D, E, C, F`
In-order:` D, B, E, A, F, C`
Post-order:` D, E, B, F, C, A`

The most common way to traverse through a tree is to use recursion. With these traversals, we rely on the call stack to navigate back up the tree when we have reached the end of a sub-path

**Pre-order**

Let’s break down the pre-order traversal. Here is the pseudocode for this traversal method:

```
ALGORITHM preOrder(root)

  OUTPUT <-- root.value

  if root.left is not NULL
      preOrder(root.left)

  if root.right is not NULL
      preOrder(root.right)

```
Pre-order means that the root has to be looked at first. In our case, looking at the root just means that we output its value. When we call preOrder for the first time, the root will be added to the call stack:

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal1.PNG)


