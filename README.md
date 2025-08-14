import java.util.ArrayList;
import java.util.Scanner;

public class StudentNotesManager {

    
    static class Note {
        String subject;
        String content;

        Note(String subject, String content) {
            this.subject = subject;
            this.content = content;
        }
    }

    static ArrayList<Note> notes = new ArrayList<>();
    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) {
        System.out.println("Welcome to Student Notes Manager ");
        int choice;
        do {
            System.out.println("\n1. Add a Note");
            System.out.println("2. View Notes");
            System.out.println("3. Exit");
            System.out.print("Choose an option: ");
            choice = sc.nextInt();
            sc.nextLine();

            switch (choice) {
                case 1 -> addNote();
                case 2 -> viewNotes();
                case 3 -> System.out.println("Goodbye! ");
                default -> System.out.println("Invalid choice. Please try again.");
            }
        } while (choice != 3);
    }

    static void addNote() {
        System.out.print("Enter subject name: ");
        String subject = sc.nextLine();
        System.out.print("Enter your note: ");
        String content = sc.nextLine();
        notes.add(new Note(subject, content));
        System.out.println(" Note saved successfully!");
    }

    static void viewNotes() {
        if (notes.isEmpty()) {
            System.out.println("No notes found. Add one first!");
        } else {
            System.out.println("\n--- Your Notes ---");
            for (Note note : notes) {
                System.out.println(" " + note.subject + ": " + note.content);
            }
        }
    }
}
