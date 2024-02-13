# Grade-calculator-
import java.util.Scanner;

public class GradeCalculator {
   public static void main(String[] args) {
       Scanner scanner = new Scanner(System.in);

       // Get the number of subjects
       System.out.print("Enter the number of subjects: ");
       int numSubjects = scanner.nextInt();

       // Declare arrays to store subject names and marks
       String[] subjects = new String[numSubjects];
       int[] marks = new int[numSubjects];

       // Get subject names and marks from the user
       for (int i = 0; i < numSubjects; i++) {
           System.out.print("Enter name of subject " + (i + 1) + ": ");
           subjects[i] = scanner.next();

           do {
               System.out.print("Enter marks obtained in " + subjects[i] + " (out of 100): ");
               marks[i] = scanner.nextInt();
           } while (marks[i] < 0 || marks[i] > 100);  // Input validation
       }

       // Calculate total marks
       int totalMarks = 0;
       for (int mark : marks) {
           totalMarks += mark;
       }

       // Calculate average percentage
       double averagePercentage = (totalMarks * 100.0) / (numSubjects * 100);

       // Calculate grade
       char grade;
       if (averagePercentage >= 90) {
           grade = 'A';
       } else if (averagePercentage >= 80) {
           grade = 'B';
       } else if (averagePercentage >= 70) {
           grade = 'C';
       } else if (averagePercentage >= 60) {
           grade = 'D';
       } else {
           grade = 'F';
       }

       // Display results
       System.out.println("\nTotal Marks: " + totalMarks);
       System.out.printf("Average Percentage: %.2f%%\n", averagePercentage);
       System.out.println("Grade: " + grade);
   }
}
