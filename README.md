# Mystery of the Linked List
 
I say it's a mystery because In preparation for job interviews I have been on sites like code wars and Leet code  solving problems. I load a question, think about it, struggle for a while, and finally have an 'aha!' moment before getting a solution.
 
 
But every once in a while I see this.
 
!["link to Google"](https://github.com/JKaram/Linked-List/blob/master/docs/desc.png?raw=true)
 
The input is looks like this
 
!["link to Google"](https://github.com/JKaram/Linked-List/blob/master/docs/Screen%20Shot%202020-01-31%20at%2010.14.35%20AM.png?raw=true)
 
 
My first reaction was that these were fancy names for arrays.
 
```
const addTwoNumbers = function(l1, l2) {
   return [l1.reduce((a,b) => a + b) + l1.reduce((a,b) => a + b)].split('');
};
```
Spoiler alert this ^^^ does not work.
 
## So what is a linked list?
 
The technical definition is...
 
'A linked list is a sequence of data structures, which are connected together via links.'
 
A linked list is a collection of elements known as nodes. If you think of  Each node containing data AND a pointer to the next node. Here is the catch. You have to start from the head and iterate through the list until you arrive on the element you want (Sequential Access).
 
![](https://github.com/JKaram/Linked-List/blob/master/docs/LinkedList.png?raw=true)
 
That explains the name.
 
##  Why use a linked list over an Array?
 
So an array and linked list are similar. But an array sounds better; you can search an array by index or value without having to iterate through it (Random Access).
 
The primary benefit of linked lists is that they can contain an arbitrary number of values while using only the amount of memory necessary for those values. Though originally intended for better memory management, linked lists also became popular when developers didn’t know how many items an array would ultimately contain. When loading an array, it takes up a whole chunk of memory. A linked list can take up tiny bits of memory scattered about. Arrays are of fixed size. In contrast, Linked lists are dynamic and flexible and can expand and contract its size.
 
In case of linked list, a new element is stored at the first free and available memory location, with only a single overhead step of storing the address of memory location in the previous node of linked list.
 
In array, Insertion and Deletion operation takes more time, as the memory locations are consecutive and fixed.
 
## How to work with a Linked List
 
As mentioned before, iterating through a linked list is a bit unintuitive.
 
```
var current = this.start;
// If the current node is not null.
while (current !== null) {
// do something which the current node
current = current.next;
// ^^^^^ Move to the next Node
}
```
 
There is no way of knowing how long a list is until you get to the last node with Null inside.
 
Here is the answer to the above question
 
```
var addTwoNumbers = function(l1, l2) {
 // Create a dummy head node because
   // we need a pointer to the first node in the solution.
 // See how we return headNode.next at the end of the code.
   let headNode = new ListNode('dummy_node');
  // Keep track of the current node so that we can easily add a new node at the end
   let currNode = headNode;
  // Value carried over from previous addition (is either 0 or 1)
   let carry = 0;
  
 // Same as:  while (l1 != null || l2 != null || carry != 0)
   while (l1 || l2 || carry) {
       let sum = carry;
       if (l1) {
           sum += l1.val;
           l1 = l1.next;
       }
       if (l2) {
           sum += l2.val;
           l2 = l2.next;
       }
       if (sum >= 10) {
       // If the sum is two digit,
     // we need to carry over 1 to the next loop
           carry = 1;
           sum -= 10;
       } else {
           carry = 0;
       }
   // Add a new node to our solution (linked list)
       currNode.next = new ListNode(sum);
  
   // advance the current node
       currNode = currNode.next;
   }
  
   return headNode.next; 
};
 
```
 
# When do you need a linked list
 
 
 
Advantages of a linked list
 
* Efficient to insert or remove items at any point in the list.
 
* Easy to grow or shrink the list; no inherent limit on list size.
 
* Memory requirements grow linearly with the list size.
 
Disadvantages:
 
* Finding the nth item is inefficient — order(list-size), vs constant-time for an array list.
 


Generally an array is what you need.


# Sources

* https://www.studytonight.com/data-structures/linked-list-vs-array
* https://leetcode.com/problems/add-two-numbers/submissions/
* https://www.geeksforgeeks.org/linked-list-vs-array/
* https://www.youtube.com/watch?time_continue=159&v=QRpbNTKH6XY&feature=emb_title




















