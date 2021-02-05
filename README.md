## Linked Lists 

<br>

## Stacks 

<br>

## Queue

<br>

## Binary Tree

<br>

* Binary Search Tree

<br>

## Heap

<br>

## Hashing 

* hash tables
hash tables allow instant look up, which make them faster and less costly in terms of big O notation 

<br>

## Graph
``` javascript
class Graph { 
    constructor() { 
    this.nodeCount = 0;
    this.nodeObj = {}; 
  } 
  createNode(node)  { 
    this.nodeObj[node]=[];
    this.nodeCount++;
   } 
  addChild(node,child){
    node != child ? this.nodeObj[node].push(child) : ''
  }

showConnections() {
const allNodes = Object.keys(this.nodeObj); 
for (let node of allNodes) {     
    let nodeConnections = this.nodeObj[node];
    let connections = ""; 
    let vertex;
    for (vertex of nodeConnections) {
        connections += vertex + " ";
    } 
        if (connections === '') {
            console.log(node + "->" + ' No children')
        } else {
            console.log(node + "-> " + connections);
        }
    } 
    } 
} 

    const myGraph = new Graph();

myGraph.createNode(1)
myGraph.createNode(2)
myGraph.createNode(3)
myGraph.createNode(4)
myGraph.createNode(5)
myGraph.createNode(6)

myGraph.addChild('1', '2')
myGraph.addChild('1', '3')
myGraph.addChild('1', '4')
myGraph.addChild('2', '5')
myGraph.addChild('3', '6')
myGraph.addChild('4', '3')
myGraph.addChild('4', '6')
myGraph.addChild('5', '6')
myGraph.addChild('5', '5')

myGraph.showConnections();
```    
<br>
<a href="https://medium.com/@ziyoshams/graphs-in-javascript-cc0ed170b156" target="_blank">graph reference</a>
## Matrix

<hr>

### extra things 

<br>

#### promises in js 

<br>

#### 'this' in js 

<br>

#### regular expressions
^ denotes things to ignore