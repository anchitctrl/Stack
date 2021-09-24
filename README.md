# Stack


## Table of Contents:
* [Implementation of Stack](#implementation-of-stack)
* [Push Operation](#push-operation)
* [Pop Operation](#pop-operation)
* [Peek Operation](#peek-operation)
* [Creation of Stack](#creation-of-stack)
* [Reverse a String using a Stack](#reverse-a-string-using-a-stack)

<a name="implementation-of-stack"></a>
## Implementation of Stack

```java
private ListNode top;
	private int length;
	
	private class ListNode {
		private int data; // Can be a generic type
		private ListNode next; // Reference to next ListNode in list
		
		public ListNode(int data) {
			this.data = data;
			this.next = null;
		}
	}
```

<a name="push-operation"></a>
## Push Operation

```java
public void push(int data) {
		ListNode temp = new ListNode(data);
		temp.next = top;
		top = temp;
		length++;
	}
```

<a name="pop-operation"></a>
## Pop Operation

```java
public int pop() {
		if(isEmpty()) {
			throw new EmptyStackException();
		}
		int result = top.data;
		top = top.next;
		length--;
		return result;
	}
```

<a name="peek-operation"></a>
## Peek Operation

```java
public int peek() {
		if(isEmpty()) {
			throw new EmptyStackException();
		}
		return top.data;
	}
```

<a name="creation-of-stack"></a>
## Creation of Stack

```java
import java.util.EmptyStackException;
 
public class Stack {
 
	private ListNode top;
	private int length;
	
	private class ListNode {
		private int data; // Can be a generic type
		private ListNode next; // Reference to next ListNode in list
		
		public ListNode(int data) {
			this.data = data;
			this.next = null;
		}
	}
	
	public Stack() {
		top = null;
		length = 0;
	}
	
	public int length() {
		return length;
	}
	
	public boolean isEmpty() {
		return length == 0;
	}
	
	public void push(int data) {
		ListNode temp = new ListNode(data);
		temp.next = top;
		top = temp;
		length++;
	}
	
	public int pop() {
		if(isEmpty()) {
			throw new EmptyStackException();
		}
		int result = top.data;
		top = top.next;
		length--;
		return result;
	}
	
	public int peek() {
		if(isEmpty()) {
			throw new EmptyStackException();
		}
		return top.data;
	}
	
	public static void main(String[] args) {
		Stack stack = new Stack();
		stack.push(10);
		stack.push(15);
		stack.push(20);
		
		System.out.println(stack.peek());
		stack.pop();
		System.out.println(stack.peek());
		stack.pop();
		System.out.println(stack.peek());
	}
}
```

<a name="reverse-a-string-using-a-stack"></a>
## Reverse a String using a Stack

```java
import java.util.Stack;
 
public class StringReverse {
	
	public static String reverse(String str) {
		Stack<Character> stack = new Stack<>();
		char[] chars = str.toCharArray();
		
		for(char c : chars) {
			stack.push(c);
		}
		
		for(int i = 0; i < str.length(); i++) {
			chars[i] = stack.pop();
		}
		return new String(chars);
	}
 
	public static void main(String[] args) {
		String str = "ABCD";
		System.out.println("Before reverse - " + str);
		System.out.println("After reverse - " + reverse(str));
	}
}
```
