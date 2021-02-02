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

<br>

## Graph
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
<br>

## Matrix

<hr>

### extra things 

<br>

#### promises in js 

<br>

#### 'this' in js 

<br>

#### regular expressions