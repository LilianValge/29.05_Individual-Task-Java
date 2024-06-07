```java
/*
Develop a simple book management application with ArrayList.
User should be able to add a book to ArrayList.
User should be able to remove a book from ArrayList.

Easy: Work with String in ArrayList. All the actions should be available for user.

*/
import java.util.ArrayList;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        var bookList = new ArrayList<String>();

        // Opening scanner for user input
        var scanner = new Scanner(System.in);

        // Adding books
        System.out.println("Enter book names to add to the list. Type 'exit' if you want to stop adding books.");
        while (true) {
            var item = scanner.nextLine(); // Asking for input
            if (item.equals("exit")) {
                break;
            }
            addItem(bookList, item);
        }

        printArrayList(bookList);

        // Removing a book
        System.out.println("Enter the name of the book you want to remove from the list:");
        var itemToRemove = scanner.nextLine(); // Asking the user for input
        removeItem(bookList, itemToRemove);

        printArrayList(bookList);

        scanner.close();
    }

    // Going through elements
    public static void printArrayList(ArrayList<String> items) {
        System.out.println("Current list of books is following:");
        for (String item : items) {
            System.out.println(item);
        }
    }

    // Adding an item to the list
    public static void addItem(ArrayList<String> items, String item) {
        items.add(item);
        System.out.println(item + " has been added to the list.");
    }

    // Removing an item from the list
    public static void removeItem(ArrayList<String> items, String item) {
        if (items.remove(item)) {
            System.out.println(item + " has been removed from the list.");
        } else {
            System.out.println(item + " was not found in the list.");
        }
    }
}
```
