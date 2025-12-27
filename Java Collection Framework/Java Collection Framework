// src/CollectionFrameworkDemo.java
// Java Collection Framework - Complete Project with 6 Tasks
// All implementations use core Java collections with detailed comments

import java.util.*;

class Student {
    String id, name, dept;
    
    Student(String id, String name, String dept) {
        this.id = id; this.name = name; this.dept = dept;
    }
    
    @Override
    public String toString() {
        return id + ": " + name + " (" + dept + ")";
    }
}

class Employee {
    String id, department;
    
    Employee(String id, String dept) {
        this.id = id; this.department = dept;
    }
    
    @Override
    public String toString() {
        return id + " -> " + department;
    }
}

public class CollectionFrameworkDemo {
    
    //Kth smallest element in ArrayList using PriorityQueue (MaxHeap)
    public static Integer findKthSmallest(ArrayList<Integer> arr, int k) {
        // Create max-heap of size k to keep k largest elements seen so far
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>((a,b) -> b - a);
        
        for (int num : arr) {
            maxHeap.offer(num);
            if (maxHeap.size() > k) {
                maxHeap.poll();  // Remove largest from heap
            }
        }
        return maxHeap.peek();  // Root is kth smallest
    }
    
    //TreeMap for word frequencies in text
    public static TreeMap<String, Integer> wordFrequencies(String text) {
        TreeMap<String, Integer> freqMap = new TreeMap<>();
        String[] words = text.toLowerCase().split("[^a-zA-Z]+");  // Split by non-letters
        
        for (String word : words) {
            if (!word.isEmpty()) {
                freqMap.put(word, freqMap.getOrDefault(word, 0) + 1);
            }
        }
        return freqMap;
    }
    
    // Custom comparator for PriorityQueue - priority by length then alphabetical
    static class StringComparator implements Comparator<String> {
        @Override
        public int compare(String a, String b) {
            if (a.length() != b.length()) {
                return b.length() - a.length();  // Longer strings first
            }
            return a.compareTo(b);  // Alphabetical for same length
        }
    }
    
    //Queue and Stack using PriorityQueue
    static class PriorityQueueStack<E> {
        private PriorityQueue<E> pq = new PriorityQueue<>();
        
        public void push(E item) { pq.offer(item); }
        public E pop() { return pq.poll(); }
        public E peek() { return pq.peek(); }
        public boolean isEmpty() { return pq.isEmpty(); }
    }
    
    static class PriorityQueueQueue<E> {
        private PriorityQueue<E> pq = new PriorityQueue<>();
        
        public void offer(E item) { pq.offer(item); }
        public E poll() { return pq.poll(); }
        public E peek() { return pq.peek(); }
        public boolean isEmpty() { return pq.isEmpty(); }
    }
    
    //TreeMap for student details (sorted by ID)
    public static TreeMap<String, Student> createStudentMap() {
        TreeMap<String, Student> studentMap = new TreeMap<>();
        studentMap.put("IT23001", new Student("IT23001", "Alice", "CSE"));
        studentMap.put("IT23005", new Student("IT23005", "Bob", "ECE"));
        studentMap.put("IT23003", new Student("IT23003", "Carol", "IT"));
        return studentMap;
    }
    
    //Check if two LinkedLists are equal
    public static <T> boolean areLinkedListsEqual(LinkedList<T> list1, LinkedList<T> list2) {
        if (list1.size() != list2.size()) return false;
        
        ListIterator<T> it1 = list1.listIterator();
        ListIterator<T> it2 = list2.listIterator();
        
        while (it1.hasNext() && it2.hasNext()) {
            if (!it1.next().equals(it2.next())) {
                return false;
            }
        }
        return true;
    }
    
    // (6) HashMap for employee departments
    public static HashMap<String, String> createEmployeeMap() {
        HashMap<String, String> empMap = new HashMap<>();
        empMap.put("EMP001", "Software Development");
        empMap.put("EMP002", "Quality Assurance");
        empMap.put("EMP003", "Database Admin");
        empMap.put("EMP004", "Network Security");
        return empMap;
    }
    
    public static void main(String[] args) {
        System.out.println("=== JAVA COLLECTION FRAMEWORK DEMO ===\n");
        
        //Kth smallest demo
        ArrayList<Integer> numbers = new ArrayList<>(Arrays.asList(7, 10, 4, 3, 20, 15));
        System.out.println("(1) Kth Smallest (k=3): " + findKthSmallest(numbers, 3));
        
        //Word frequency demo
        TreeMap<String, Integer> wordFreq = wordFrequencies("Java is great and Java is fun Java");
        System.out.println("\n(2) Word Frequencies: " + wordFreq);
        
        //PriorityQueue Stack & Queue demo
        PriorityQueueStack<String> stack = new PriorityQueueStack<>();
        stack.push("Zebra"); stack.push("Apple"); stack.push("Banana");
        System.out.println("\n(3a) Stack (Priority): " + stack.pop() + ", " + stack.pop());
        
        PriorityQueueQueue<String> queue = new PriorityQueueQueue<>(new StringComparator());
        queue.offer("Cat"); queue.offer("Dog"); queue.offer("Elephant");
        System.out.println("(3b) Queue (Priority): " + queue.poll() + ", " + queue.poll());
        
        //Student TreeMap demo
        TreeMap<String, Student> students = createStudentMap();
        System.out.println("\n(4) Students (Sorted):");
        students.forEach((id, student) -> System.out.println("  " + student));
        
        //LinkedList equality demo
        LinkedList<Integer> list1 = new LinkedList<>(Arrays.asList(1, 2, 3));
        LinkedList<Integer> list2 = new LinkedList<>(Arrays.asList(1, 2, 3));
        LinkedList<Integer> list3 = new LinkedList<>(Arrays.asList(1, 2, 4));
        System.out.println("\n(5) Lists Equal? " + areLinkedListsEqual(list1, list2) + 
                          ", " + areLinkedListsEqual(list1, list3));
        
        //Employee HashMap demo
        HashMap<String, String> employees = createEmployeeMap();
        System.out.println("\n(6) Employees:");
        employees.forEach((id, dept) -> System.out.println("  " + id + " -> " + dept));
        
        System.out.println("\n=== All Tasks Completed Successfully! ===");
    }
}
