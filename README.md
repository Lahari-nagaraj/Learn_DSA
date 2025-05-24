# Linked List

Arraylist:
Insert - O(n) ,  Search - O(1)
LinkedList:
Insert : O(1) , Search : O(n)

``` syntax
Node head;
class Node{
String data;
Node next;

Node(String data){
this.data = data;
this.next = null;
}
}
```
To find size:
create a private variable with constructor with initial value set to 0 then increase or decrease the value based on function

### Using collection framework

``` syntax
import java.util.LinkedList;
LinkedList<String> list = new LinkedList<>();
list.add("Apple");
list.addFirst("Mango");    // Add at the beginning
list.addLast("Orange");    // Add at the end
String first = list.getFirst();
String last = list.getLast();
String element = list.get(2); // Get element at index 2
list.remove("Banana");    // Removes the first occurrence
list.removeFirst();       // Removes the first element
list.removeLast();        // Removes the last element
list.remove(1);           // Removes element at index 1
for (String fruit : list) {
    System.out.println(fruit);   //Using for-each
}
list.size();
list.contains("Apple");
list.clear(); // Removes all elements
list.isEmpty();              // Checks if list is empty
```

## Reversing a linkedlist

#### 1. Iterative 
#### 2. Recursive
