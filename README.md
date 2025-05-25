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
list.addFirst("Mango");                     // Add at the beginning
list.addLast("Orange");                    // Add at the end
String first = list.getFirst();
String last = list.getLast();
String element = list.get(2);              // Get element at index 2
list.remove("Banana");                     // Removes the first occurrence
list.removeFirst();                       // Removes the first element
list.removeLast();                        // Removes the last element
list.remove(1);                          // Removes element at index 1
for (String fruit : list) {
    System.out.println(fruit);            //Using for-each
}
list.size();
list.contains("Apple");
list.clear();                           // Removes all elements
list.isEmpty();                        // Checks if list is empty
```

## Reversing a linkedlist

#### 1. Iterative 
``` code
public void reverseIterate(){
if(head == null || head.next == null){
return;
}
Node prevNode = head;
Node currNode = head.next;
while(currNode != null){
Node nexxtNode = currNode.next;
currNode.next = prevNode;
//update
prevNode = currNode;
currNode = nextNode;
}
head.next = null;
hed = prevNode;
}
```
#### 2. Recursive
``` code
public Node reverseRecursive(Node head){
if(head == null || head.next ==null){
return head;
}
Node newhead = reverseRecursive(head.next);
head.next.next = head;   //points back 
head.next = null;
return newhead
}
```

1. Delete nth node from last : find size, (size-n+1 from first)
2. Palindrome Linkedlist: find the middle of ll, reverse second half, compare the elements
``` palindrome
public boolean isPalindrome(ListNode head){
if(head == null|| head.next == null){
return true;
}
ListNode middle = findMiddle(head);
ListNode secondhalfstart = reverse(middle.next);
//compare
ListNode firsthalfhead = head;
while(secondhalfstart != null){
if(firsthalfstart.val != secondhalfstart.val){
return false;
}
firsthalfstart = firsthalfstart.next;
secondhalfstart = secondhalstart.next;
}
return true;
}
```
### Hare and turtle
to find the middle element of linkedlist, when turtle moves one step hare moves 2 steps. until hare's next jum != null turtlr value keeeps on increasing else, turtles location is the middle value in a linkedlist
```code
public ListNode findMiddle(ListNode head){
ListNode hare = head;
ListNode turtle = head;
while(hare.next != null && hare.next.next != null){
hare = hare.next.next;
turtle = turtle.next;
}
return turtle;
}
```
3. Detect a cycle in a linkedlist:
   
