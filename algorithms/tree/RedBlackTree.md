# Red Black Tree
## Property
1. Each node are either red or black.
2. The root should be black, but not necessary.
3. All leaf(NIL) are black.
4. If a node is red, it's children are black.
5. Every path from a given node to any of it's leaf(NIL) contains same numbers of black nodes.

**Black Depth**: The number of black nodes from root to leaf.

### The path from the root to the farthest leaf is **no more than twice** as long as the path from the root to the nearest leaf.
It's because the combination between property 4 and 5. As we get a shortest path, which all the nodes are black, with B black nodes, according to property 5, the longest path should also contains exact B black nodes. However, according to property 4, the longest path could only contains also B red nodes, therefore, the longest path is no more than twice as long as the shortest path.


**The example code of TreeNode & RBT**
```
// C++ code
#include <iostream>
#include <string>
class RBT;
class TreeNode{
private:
    TreeNode *leftchild;
    TreeNode *rightchild;
    TreeNode *parent;
    std::string element;
    int key;
    int color;         // 0: Red, 1: Black; using type:bool is ok
    friend RBT;
    ...
}
class RBT{
private:
    TreeNode *root;
    TreeNode *neel;    // This is NIL, often called sentinel
    ...
}
```
## Rotation
To keep the tree with the red-black tree property when we insert/delete an element to/from a red-black tree, we needs rotation to balance the tree structure.

refs: http://alrightchiu.github.io/SecondRound/red-black-tree-rotationxuan-zhuan.html

### Left rotation
![RBT left rotation](https://github.com/alrightchiu/SecondRound/blob/master/content/Algorithms%20and%20Data%20Structures/Tree%20series/RBT_fig/Rotation/rotate6.png?raw=true)

```
// C++ code
void RBT::LeftRotation(TreeNode *x){

    TreeNode *y = x->rightchild;         // assume y is the right child of x, which will finally be x's parent.

    x->rightchild = y->leftchild;        // let x's right child point to y's current left child.

    if (y->leftchild != neel){           // if y's current left child is NIL, the operation is unnecessary.
        y->leftchild->parent = x;        // let parent of y's left child point to x, i.e. x will be the new parent of y's current left child.
    }

    y->parent = x->parent;               // let parent of y be the current parent of x.

    if (x->parent == neel){              // if x is root, then y will be the new root.
        root = y;          
    }         
    else if (x == x->parent->leftchild){ // if x is the left child of it's parent...
        x->parent->leftchild = y;        // y will be the new left child of it's parent.
    }
    else{                                // if x is the right child of it's parent...
        x->parent->rightchild = y;       // x will be the new right child of it's parent.
    }
    y->leftchild = x;                    // let x be the left child of y.
    x->parent = y;                       // Finally, y is x's new parent.
}
```

### Right rotation
Similar to left rotation.
![RBT right rotation](https://github.com/alrightchiu/SecondRound/blob/master/content/Algorithms%20and%20Data%20Structures/Tree%20series/RBT_fig/Rotation/rotate11.png?raw=true)

```
// C++ code
void RBT::RightRotation(TreeNode *y){

    TreeNode *x = y->leftchild;           // assume x is the left child of y

    y->leftchild = x->rightchild;         // let y's left child point to x's right child
    if (x->rightchild != neel){           // if the right child of x is not NIL, then let it's parent point to y
        x->rightchild->parent = y;
    }
    x->parent = y->parent;                // let x's parent point to y's parent

    if (y->parent == neel){               // if y is root, let x be the new root
        root = x;          
    }              
    else if (y == y->parent->leftchild){  // if y is currently the left child of it's parent...
        y->parent->leftchild = x;         // let x be the new left child of it's parent
    }
    else{                                 // if y is currently the right child of it's parent...
        y->parent->rightchild = x;        // let x be the new right child of it's parent
    }
    x->rightchild = y;                    // let y be the right child of x
    y->parent = x;                        // let x be the parent of y
}
```

## Insertion
Since red-black tree belongs to binary search tree, when we insert an element, it should satisfy: Key(L) < Key(current) < Key(R), which is similar to BST insertion.

However, there's more in red-black tree insertion:
1. NIL: All pointers point to null should be point to NIL in RBT.
2. Color: Normally, we add a new node with red color. If the parent of the new node is a black node, it satisfy the specification of RBT, however, if the parent is a red node, we need to use rotation to satisfy RBT.

Here we use InsertRBT() to insert a node, and InsertFixedUpRBT(), called by InsertRBT(), to fixed our tree to satisfy the specification of RBT.

```
// C++ code
void RBT::InsertRBT(int key, string str){
    // The logic of first half is same as InsertBST, except we need to change NULL to NIL
    TreeNode *y = neel;
    TreeNode *x = root;
    TreeNode *insert_node = new TreeNode(key, str);

    while (x != neel) {     // Initial root as NIL and determine here.
        y = x;
        if (insert_node->key < x->key){
            x = x->leftchild;
        }
        else{
            x = x->rightchild;
        }
    }

    insert_node->parent = y;

    if (y == neel){
        this->root = insert_node;
    }
    else if (insert_node->key < y->key){
        y->leftchild = insert_node;
    }
    else{
        y->rightchild = insert_node;
    }

    // The children of new node are NIL, and the color of new node should be red
    insert_node->leftchild = neel;
    insert_node->rightchild = neel;
    insert_node->color = 0;

    InsertFixedUpRBT(insert_node);      // The function to fix the tree to satisfy RBT
}
```
### Fix up RBT
#### When do we need to fix up RBT?
When the new red node is the child of a red node.

![Fix RBT](https://github.com/alrightchiu/SecondRound/blob/master/content/Algorithms%20and%20Data%20Structures/Tree%20series/RBT_fig/Insert/insert1.png?raw=true)

According to the picture above, when we want to insert a new node to node X:
- node(X) is the parent, and it's red.
- node(Y) is the uncle, and it could be either red or black.
- node(Z) is the grandparent, and it's black, since X is red.
- node(W) could be either red or black.
- All gray nodes are independent to the operation-- insert a node to X--.

According to uncle's color, there are three different cases:
1. case1: uncle is red
2. case2: uncle is black, and the new node is the right child of node(X)
3. case3: uncle is black, and the new node is the left child of node(X)

#### Case1

```

```
