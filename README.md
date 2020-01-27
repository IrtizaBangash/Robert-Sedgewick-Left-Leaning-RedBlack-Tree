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
