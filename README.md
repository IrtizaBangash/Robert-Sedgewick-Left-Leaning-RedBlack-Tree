# Robert-Sedgewick-Left-Leaning-RedBlack-Tree
Irtiza Bangash, Khurram Khalil, Fatima Ilyas
## Function Calls:

### 1:Insert Function call

```
#testing insert function
llrb = LLRB()
for i in range(50):
    #insert function
    llrb.insert(i)
    
#returns the nodes of tree inorder
#not necessary to run
print(llrb.root.inOrder())

#for graphical representation of the tree
plot_tree(llrb.root, figsize=(10,2))
```
if the nodes on matplotlib window are conjusted, stretch the window a bit.

### 2:Delete Function call
Only takes an existing node as argument.
Do not enter any value which is not already present in the tree already. Doing so will raise a NoneType error.
```
#testing delete function
llrb = LLRB()
for i in range(50):
    llrb.insert(i)

#not necessary to run
print(llrb.root.inOrder())

plot_tree(llrb.root, figsize=(10,2))
llrb.delete(50)
plot_tree(llrb.root, figsize=(10,2))
```
if the nodes on matplotlib window are conjusted, stretch the window a bit.

### 3:Search Function call
Takes any value as an input. But the value should be of the same data type.
Looks up a value and returns true if it exists, false otherwise.
```
#testing search function
llrb = LLRB()
for i in range(50):
    llrb.insert(i)

print(llrb.Search(46))
print(llrb.Search(100))
```

## Code used for visual representation of tree.
pylab and matplotlib packages must be downloaded.
```
import matplotlib.pyplot as plt
from matplotlib import rcParams
import pylab

#a graphical representation of the left leaning red black tree (plot_tree, below, uses plot_node)
def plot_node(node, rb=True, level=1, posx=0, posy=0):
    width = 2000.0 * (0.5 ** (level))  # This will be used to space nodes horizontally
    if node.color == 0 or rb == False:
        plt.text(posx, posy, str(node.data), horizontalalignment='center', color='k', fontsize=10)
    else:
        plt.text(posx, posy, str(node.data), horizontalalignment='center', color='r', fontsize=10)

    if node.left:
        px = [posx, posx - width]
        py = [posy - 1, posy - 15]
        if node.left.color == 0 or rb == False:
            plt.plot(px, py, 'k-')#, hold=True
        else:
            plt.plot(px, py, 'r-')#, hold=True
        plot_node(node.left, rb, level + 1, posx - int(width), posy - 20)

    if node.right:
        plot_node(node.right, rb, level + 1, posx + int(width), posy - 20)
        px = [posx, posx + width]
        py = [posy - 1, posy - 15]
        if node.right.color == 0 or rb == False:
            plt.plot(px, py, 'k-')#, hold=True
        else:
            plt.plot(px, py, 'r-')#, hold=True


def plot_tree(node, figsize=(10, 6)):
    if node.color == True:
        rb = False
    else:
        rb = True
    rcParams['figure.figsize'] = figsize
    fig, ax = plt.subplots()
    ax.axis('off')
    plot_node(node, rb)
    plt.show()
```

