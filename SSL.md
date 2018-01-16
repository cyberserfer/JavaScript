# Singly Linked List (SLL)

Not contiguous
Data structure - formalized container

    Objects
    Arrays - uses a point in memory to store. When arrays are created they get assigned a block of memory in the heap.
    
Memory
    The Stack
    Heap - Basically a Table. Computer assigns open memory spots in the table
```    


function Node(val){
  this.val = val;
  this.next = null;
}

const node = new Node(5); // this is equal to the memory location (example D3)
                          // the "this above also becomes node which is also D3
const node2 = new Node(1)
```
To look through an object containing may Nodes(objects) you can itterate using:
```
let current = Node;
while(current.next){
    console.log(current.val);
    current=current.next;
}
// with this you could find the last one and add
node.next = new Node(val);
```
