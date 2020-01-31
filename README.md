# Linked-List

Understanding a stack structure is daunting. That is why I am not going to try to explain it … but you can read the wiki if you want. What I am going to try and explain is the mystery of the linked list. I say it's a mystery because In preparation for job interviews I have been on sites like code wars and Leet code  solving problems. I load a question, think about it, struggle for a while, and finally have an 'aha!' moment before getting a solution. 


But every once in a while I see this.

!["link to Google"](https://github.com/JKaram/Linked-List/blob/master/docs/Screen%20Shot%202020-01-31%20at%2010.38.11%20AM.png?raw=true)

The input is looks like this

!["link to Google"](https://github.com/JKaram/Linked-List/blob/master/docs/Screen%20Shot%202020-01-31%20at%2010.14.35%20AM.png?raw=true)


My first reaction was these were fancy names for arrays. 

```
const addTwoNumbers = function(l1, l2) {
    return l1.reduce((a,b) => a + b) + l1.reduce((a,b) => a + b);
};
```
Spoiler alert this ^^^ does not work.

## So what is a linked list?

The technical definition is...

'A linked list is a sequence of data structures, which are connected together via links.'

A linked list is a collection of elements known as nodes. Each node contains data AND a link to the next node.

That explains the name. Why use a linked list over an Array?






Linked list is considered as non-primitive data structure contains a collection of unordered linked elements known as nodes.
2. In the array the elements belong to indexes, i.e., if you want to get into the fourth element you have to write the variable name with its index or location within the square bracket.
3. In a linked list though, you have to start from the head and work your way through until you get to the fourth element.
4. Accessing an element in an array is fast, while Linked list takes linear time, so it is quite a bit slower.
5. Operations like insertion and deletion in arrays consume a lot of time. On the other hand, the performance of these operations in Linked lists is fast.
6. Arrays are of fixed size. In contrast, Linked lists are dynamic and flexible and can expand and contract its size.



