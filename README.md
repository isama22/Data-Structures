## Linked Lists 
<a href="https://medium.com/better-programming/how-to-implement-a-linked-list-using-javascript-387729416a5b" target="_blank">reference 1</a> 
| 
<a href="https://www.geeksforgeeks.org/implementation-linkedlist-javascript/" target="_blank">reference 2</a>
* a linked list stores information, with each item pointing to the next one, similar to linked paperclip. each item is a node and the list has a head and tail node. 
* it's very quick in terms of big O because of how fast it is to add items to the end. and it's very flexible on size, you can keep adding items on as long as there's space on your machine. but look ups are costly because you have to walk the length of the list to find something
* doubly linked lists have each node pointing to the node before and behind it. singly linked lists give you no way of looking at the node behind
* useful with stacks and queues because you only need to operate on the ends
![](https://i.postimg.cc/sxKWrX7d/Screen-Shot-2021-02-05-at-5-51-25-PM.png)
<br>

``` javascript
class Node {
  // constructor
  constructor(element) {
    this.element = element;
    this.next = null;
  }
}

// linkedlist class
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }
  add(element) {
    // creates a new node
    var node = new Node(element);
    // to store current node
    var current;
    // if list is Empty add the
    // element and make it head
    if (this.head == null) this.head = node;
    else {
      current = this.head;
      // iterate to the end of the
      // list
      while (current.next) {
        current = current.next;
      }
      // add node
      current.next = node;
    }
    this.size++;
  }

  removeElement(element) {
    var current = this.head;
    var prev = null;

    // iterate over the list
    while (current != null) {
      // comparing element with current
      // element if found then remove the
      // and return true
      if (current.element === element) {
        if (prev == null) {
          this.head = current.next;
        } else {
          prev.next = current.next;
        }
        this.size--;
        return current.element;
      }
      prev = current;
      current = current.next;
    }
    return -1;
  }
  removeFrom(index) {
    if (index > 0 && index > this.size) return -1;
    else {
      var curr,
        prev,
        it = 0;
      curr = this.head;
      prev = curr;

      // deleting first element
      if (index === 0) {
        this.head = curr.next;
      } else {
        // iterate over the list to the
        // position to removce an element
        while (it < index) {
          it++;
          prev = curr;
          curr = curr.next;
        }

        // remove the element
        prev.next = curr.next;
      }
      this.size--;

      // return the remove element
      return curr.element;
    }
  }
  insertAt(element, index) {
    if (index > 0 && index > this.size) return false;
    else {
      // creates a new node
      var node = new Node(element);
      var curr, prev;

      curr = this.head;

      // add the element to the
      // first index
      if (index == 0) {
        node.next = this.head;
        this.head = node;
      } else {
        curr = this.head;
        var it = 0;

        // iterate over the list to find
        // the position to insert
        while (it < index) {
          it++;
          prev = curr;
          curr = curr.next;
        }
      }
      this.size++;
    }
  }
  indexOf(element) {
    var count = 0;
    var current = this.head;

    // iterae over the list
    while (current != null) {
      // compare each element of the list
      // with given element
      if (current.element === element) return count;
      count++;
      current = current.next;
    }

    // not found
    return -1;
  }
  isEmpty() {
    return this.size == 0;
  }
  size_of_list() {
    console.log(this.size);
  }
  printList() {
    var curr = this.head;
    var str = '';
    while (curr) {
      str += curr.element + ' ';
      curr = curr.next;
    }
    console.log(str);
  }
}
// creating an object for the
// Linkedlist class
var ll = new LinkedList();

// testing isEmpty on an empty list
// returns true
console.log(ll.isEmpty());

// adding element to the list
ll.add(10);

// prints 10
ll.printList();

// returns 1
console.log(ll.size_of_list());

// adding more elements to the list
ll.add(20);
ll.add(30);
ll.add(40);
ll.add(50);

// returns 10 20 30 40 50
ll.printList();
console.log(ll)
``` 

## Stacks 

<br>

## Queue

<br>

## Binary search
* depth first search
* breadth first search 

<br>

* Binary Search Tree

<br>

## Heap

<br>

## Hashing 

* hash tables allow instant look up, which make them faster and less costly in terms of big O notation 

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
/g = global
/i = ignore case / case insensitive
.match() is pretty useful 

<hr>

### notes on react

some resources
* <a href="https://bitsofco.de/what-i-wish-i-knew-about-react/" target="_blank">what i wish i knew about react</a>
* <a href="https://obedparla.com/code/a-visual-guide-to-react-mental-models/" target="_blank">a visual guide to react mental models</a>
* <a href="https://www.freecodecamp.org/news/the-react-cheatsheet-for-2020/" target="_blank">react cheat sheet</a>
* <a href="https://snook.ca/archives/javascript/difficulty-with-react" target="_blank">why did i have difficulty learning react</a>

* <a href="https://hackernoon.com/13-things-you-need-to-know-about-react-d2e6a6422552" target="_blank">13 things to know about react</a>

* <a href="https://codeburst.io/image-uploading-using-react-and-node-to-get-the-images-up-c46ec11a7129" target="_blank">mern image upload</a>

* <a href="https://www.jamesqquick.com/courses/design-and-build-a-chat-app-with-socket-io" target="_blank">build a chat app with socket</a>

<a href="https://www.firsttimersonly.com/" target="_blank">open source contribution resource :: intro</a>


## vanilla js tips
* urnary operator ( + ) works similarly to parseInt()
* number to binary 
``` javascript 
return(num >>> 0).toString(2)
```
* last item of an array 
``` javascript 
arr[arr.length - 1]
```
* making an object out of two arrays where {arr1[0] : arr2[0]} {key: value}
```javascript
function jobs(names, jobs){
  return Object.assign(...names.map((k, i) => ({[k]: jobs[i]})))
}
console.log(jobs(["Dennis", "Vera", "Mabel", "Annette", "Sussan"],["Butcher", "Programmer", "Doctor", "Teacher", "Lecturer"]))
```
* remove duplicates from an array by using spread syntax and the Set constructor 
```javascript
function set(arr){
  return [...new Set(arr)]
}
console.log(set([1,1,3]))
```