//Asad Ali


public class Main {

	    // Node class for singly linked list
	    static class Node {
	        int value;
	        Node next;

	        Node(int value) {
	            this.value = value;
	            this.next = null;
	        }
	    }

	    // Singly Linked List class
	    static class SinglyLinkedList {
	        Node head;

	        // Add value to end of the list
	        void append(int value) {
	            Node newNode = new Node(value);
	            if (head == null) {
	                head = newNode;
	                return;
	            }
	            Node current = head;
	            while (current.next != null) {
	                current = current.next;
	            }
	            current.next = newNode;
	        }

	        // Sum of all node values
	        int sum() {
	            int total = 0;
	            Node current = head;
	            while (current != null) {
	                total += current.value;
	                current = current.next;
	            }
	            return total;
	        }

	        // Print all values in the list
	        void printList() {
	            Node current = head;
	            while (current != null) {
	                System.out.print(current.value);
	                if (current.next != null) System.out.print(" -> ");
	                current = current.next;
	            }
	            System.out.println();
	        }
	    }

	    // Check if a number is prime
	    static boolean isPrime(int n) {
	        if (n < 2) return false;
	        if (n == 2) return true;
	        if (n % 2 == 0) return false;
	        for (int i = 3; i * i <= n; i += 2) {
	            if (n % i == 0) return false;
	        }
	        return true;
	    }

	    // Check if number contains digit '3'
	    static boolean containsDigitThree(int n) {
	        return String.valueOf(n).contains("3");
	    }

	    public static void main(String[] args) {
	        int n = 100; // You can change this up to 999999

	        SinglyLinkedList primeList = new SinglyLinkedList();
	        SinglyLinkedList primesWith3 = new SinglyLinkedList();

	        // Populate prime list
	        for (int i = 2; i <= n; i++) {
	            if (isPrime(i)) {
	                primeList.append(i);
	                if (containsDigitThree(i)) {
	                    primesWith3.append(i);
	                }
	            }
	        }

	        // Display results
	        System.out.print("Primes containing digit '3': ");
	        primesWith3.printList();
	        System.out.println("Sum of primes containing digit '3': " + primesWith3.sum());
}
	}
