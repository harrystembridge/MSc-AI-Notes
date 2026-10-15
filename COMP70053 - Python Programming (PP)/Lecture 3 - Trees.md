---
flashcards:
  q-rmdu: { nid: 1791901339393, hash: a7yevass, sync: j2r9nw3m }
  q-hjxz: { nid: 1791901339420, hash: x9sbsf4r, sync: jrvxv6nt }
  q-4bpq: { nid: 1791901339438, hash: y4duz9g5, sync: ck2yu9rm }
  q-fwrz: { nid: 1791901339471, hash: dtfddzqf, sync: y3x3rzbi }
  q-ym7p: { nid: 1791901339505, hash: rkq87yf9, sync: m8u65uhh }
  q-vd5h: { nid: 1791901339519, hash: x9qxdqz3, sync: u2iyps6v }
  q-zd9g: { nid: 1791901339539, hash: nqkk98zx, sync: bpsjziyp }
  q-gxk8: { nid: 1791901339569, hash: qnpftxcc, sync: 99ts3r7r }
  q-hvgh: { nid: 1791901339589, hash: ja2cjdh9, sync: gadhhrmi }
  q-wbvy: { nid: 1791901339619, hash: ux23c2pe, sync: dexifbgv }
  q-h3w2: { nid: 1791901339639, hash: jqwzu7ia, sync: 7nh74tqh }
  q-4rw3: { nid: 1791901339669, hash: 8ffvdxs9, sync: id8t5dt5 }
  q-hz35: { nid: 1791901339690, hash: h8b5wgae, sync: xd4xy97y }
  q-e6ei: { nid: 1791901339720, hash: y8jsxg8e, sync: ayfctqmi }
  q-kq37: { nid: 1791901339738, hash: rdvfvfj6, sync: kwi5bdzg }
  q-5xa6: { nid: 1791901339770, hash: 5wfvvyt9, sync: e9pd8pkx }
  q-7b8z: { nid: 1791901339790, hash: 6qyjttre, sync: hheyxfpt }
  q-bj2y: { nid: 1791901339819, hash: p9ju5ktv, sync: vc356w7d }
---

![[Python - Lecture 3.pdf]]

> [!CARD] What is a Node in a tree?
> A basic unit of a tree that stores a value and (optionally) links to child nodes.
>
^q-rmdu

> [!CARD] What is the Root node of a tree?
> The single top-most node of a tree, which has no parent.
>
^q-hjxz

> [!CARD] What is a Parent node?
> A node that has one or more child nodes connected below it.
>
^q-4bpq

> [!CARD] What is a Child node?
> A node directly connected below another node (its parent).
>
^q-fwrz

> [!CARD] What are Siblings in a tree?
> Nodes that share the same parent.
>
^q-ym7p

> [!CARD] What is a Leaf node (also called a Terminal node)?
> A node with no children.
>
^q-vd5h

> [!CARD] What is an Internal node (also called Non-terminal, Intermediate, or Branch node)?
> A node that has at least one child (i.e. it is not a leaf).
>
^q-zd9g

> [!CARD] What is an Edge (also called a Branch) in a tree?
> The connection/link between a parent node and a child node.
>
^q-gxk8

> [!CARD] What is an Ancestor of a node?
> Any node on the path from that node up to the root (its parent, grandparent, etc.).
>
^q-hvgh

> [!CARD] What is a Subtree?
> A node together with all of its descendants, treated as a tree in its own right.
>
^q-wbvy

> [!CARD] What is the Depth of a node?
> The number of edges on the path from that node up to the root.
>
^q-h3w2

> [!CARD] What is the Height of a tree?
> The maximum number of edges on any path from the root down to a leaf.
>
^q-4rw3

> [!CARD] What makes a graph NOT a tree?
> If it has a cycle, more than one root (disconnected parts), or a node with more than one parent (inbound edge).
>
^q-hz35

> [!CARD] What is a Binary Tree?
> A tree in which every node has at most two children, typically called the left child and the right child.
>
^q-e6ei

> [!CARD] What is a Binary Search Tree (BST)?
> A binary tree where, for every node, all values in its left subtree are ≤ its value and all values in its right subtree are > its value — enabling efficient search.
>
^q-kq37

> [!CARD] What is Inorder traversal (of a binary tree)?
> Visit Left subtree → Node (Value) → Right subtree (LVR).
>
^q-5xa6

> [!CARD] What is Preorder traversal (of a binary tree)?
> Visit Node (Value) → Left subtree → Right subtree (VLR).
>
^q-7b8z

> [!CARD] What is Postorder traversal (of a binary tree)?
> Visit Left subtree → Right subtree → Node (Value) (LRV).
^q-bj2y


* Binary tree, each node has maximum 2 child nodes
* 