Download Link: https://assignmentchef.com/product/solved-list-assignment-always-sorted-linked-list
<br>
For this assignment, you will need to turn in your .java files that contain the implementation of the linked list as described below and any additional .java files you use to test it.Additionally, you can find information on Sorted Lists in Chapter 16 (4th edition) or Chapter 17 (5th edition).

Always Sorted Linked List

You are to implement a linked list that remains sorted. The linked list should be able to store any object if the object has implemented the Comparable interface. You may create either a singly linked sorted list or a doubly linked sorted list.

To start out, the list should be ordered in ascending order. This can change if the reverse method is called. If the reverse method is called and the list is in ascending order, then the list should change to be in descending order. If the list is in descending order and the reverse method is called, then the list should change to be in ascending order.

The header for the class should look like this (you can use a different class name. This is just to show the generics)

<strong>public</strong> <strong>class</strong> SortedLinkedList&lt;T <strong>extends</strong> Comparable&lt;? super T&gt;&gt;

The node class will only need the generic &lt;E&gt; since the generic T is used and is guaranteed to have the compareTo method.

<strong>private</strong> <strong>class</strong> Node&lt;E&gt;

If you separate the Node class to its own Java file then you will need to make it public and include it with your linked list implementation when you submit it.

Methods to Implement

Below are the methods you need to implement to get full credit. In addition to these methods you may implement any additional helper methods that should be kept private.

<ol>

 <li><strong>clear</strong> – Should reset the list to be empty. Can be called in the default constructor.</li>

 <li><strong>getSize</strong> – Returns the size of the list.</li>

 <li><strong>toString</strong> – Returns a string representation of the list.</li>

 <li><strong>add</strong> – Adds a new object to the list in it’s sorted position. Starts adding elements in ascending order. If the reverse method has been called, then the order is changed from ascending to descending and vice versa.

  <ol>

   <li>If the list is in ascending order then the newData needs to be placed in the list such that node.prev.data ≤ newData ≤ node.next.data.</li>

   <li>If the list is in descending order then the newData needs to be placed in the list such that node.prev.data ≥ newData ≥ node.next.data.</li>

  </ol></li>

 <li><strong>remove</strong> – Removes an item from a given index. If the position is out of bounds, then throw an IndexOutOfBoundsException. If the list is empty, then throw a EmptyCollectionException. Returns the object being removed at the index.</li>

 <li><strong>removeAll</strong> – Removes all of a given item. If the list is empty, then throw a EmptyCollectionException.</li>

 <li><strong>get</strong> – Returns the item from a given position. If the position is out of bounds, then throw an IndexOutOfBoundsException.</li>

 <li><strong>reverse</strong> – Reverses the list. If the list is in ascending order, then the list should end up in descending order and vice versa. This will also affect how add behaves. This should physically flip the list in memory so that the object at heads is at tails and vice versa. If the list is in ascending order and reverse is called you should end up with the following.

  <ol>

   <li>List: a b c d e f</li>

   <li>reverse is called</li>

   <li>List: f e d c b a</li>

   <li>reverse is called</li>

   <li>List: a b c d e f</li>

  </ol></li>

 <li><strong>contains</strong> – Takes an element and returns true if the element is in the list and false if it does not.</li>

</ol>

You should test your code as you see appropriate. Here is an example procedure you may take written in pseudocode. This doesn’t test everything. For instance, what happens if you have an empty list, call reverse, then start adding elements. It should end up in descending order.

sll = new SortedLinkedList&lt;String&gt;()sll.add(“e”)

sll.add(“c”)

sll.add(“a”)

print(sll) //should have output to show a c e. Can look different //like [a, c, e] or (a, c, e) or a c e.sll.reverse()

print(sll) //e c a.sll.add(“d”)

print(sll) //e d c a.

sll.reverse()

print(sll) //a c d e.sll.add(“d”)

sll.add(“d”)

print(sll) //a c d d d eprint(sll.get(5)) //eprint(sll.contains(“d”)) //trueprint(sll.contains(“f”)) //falsesll.removeAll(“d”)

print(sll) //a c eprint(sll.getSize()) // 3sll.removeFromIndex(2)

print(sll) //a csll.clear()sll.removeFromIndex(2) //Should throw an exception

When you add an element, you may not just add it to the front or back of the list then call a sort method. The element must be placed in it’s sorted position in BigO(N) time. Furthermore, your contains method should also be BigO(N) time. Don’t waste effort trying to implement a binary search as this may result in longer wait times. Linear traversal is fine.

What you need to turn in

All .java files you write to implement the data structure for this assignment. This does not include the already provided class files given to you.

Code that does not compile will result in a 0.