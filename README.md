# Algorithms_DataStructures
#Some snippets from a course  I am taking on Algorithms and Data Structures

#//Distance between two points

class Point {
    constructor(x, y){
        this.x = x;
        this.y = y;
    }

    static distance(a, b){
        const dx = a.x - b.x;
        const dy = a.y - b.y;

        return Math.hypot(dx, dy);
    }
}

const p1 = new Point(5, 5);
const p2 = new Point(10, 10);


#// Singly Linked list with pop, push, and shift.

class Node{
    constructor(val){
        this.val = val;
        this.next = null;
    }
}

class SinglyLinkedList{
    constructor(){
        this.length = 0;
        this.head = null;
        this.tail = null;
    }
    push(val){
        var newNode = new Node(val);
        if(!this.head){
            this.head = newNode;
            this.tail = this.head;
        } else {
            this.tail.next = newNode;
            this.tail = newNode;
        }
        this.length++;
        return this;
    }
    traverse(){
         var current = this.head;
         while(current){
         console.log(current.val)
         current = current.next
         } 
     }
    pop(){
        if(!this.head) return undefined;
        var current = this.head;
        var newTail = current;
        while(current.next){
            newTail = current;
            current = current.next;
        }
        this.tail = newTail;
        this.tail.next = null;
        this.length--;
        if(this.length === 0){
            this.head = null;
            this.tail = null;
        }
        return current;
    }
    
    shift(){
        if(!this.head) return undefined;
        var oldHead = this.head;
        this.head = oldHead.next;
        this.length--;    
        return oldHead;    
    }
}

var list = new SinglyLinkedList()
list.push("Hello")
list.push("Goodbye")
