import java.io.*;
import java.util.Scanner;

public class FileEncryptionDecryption {

    // Method to encrypt or decrypt a file
    public static void processFile(String inputFilePath, String outputFilePath, int key, boolean encrypt) {
        try (BufferedReader reader = new BufferedReader(new FileReader(inputFilePath));
             BufferedWriter writer = new BufferedWriter(new FileWriter(outputFilePath))) {

            String line;
            while ((line = reader.readLine()) != null) {
                StringBuilder processedLine = new StringBuilder();

                for (char c : line.toCharArray()) {
                    if (encrypt) {
                        processedLine.append((char) (c + key)); // Encrypt by shifting forward
                    } else {
                        processedLine.append((char) (c - key)); // Decrypt by shifting backward
                    }
                }
                writer.write(processedLine.toString());
                writer.newLine();
            }

            System.out.println("File processed successfully: " + outputFilePath);
        } catch (IOException e) {
            System.out.println("Error processing the file: " + e.getMessage());
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Choose an option:");
        System.out.println("1. Encrypt a file");
        System.out.println("2. Decrypt a file");
        int choice = scanner.nextInt();
        scanner.nextLine(); // Consume the newline character

        System.out.print("Enter the file path: ");
        String inputFilePath = scanner.nextLine();

        System.out.print("Enter the output file path: ");
        String outputFilePath = scanner.nextLine();

        System.out.print("Enter the key (integer): ");
        int key = scanner.nextInt();

        boolean encrypt = (choice == 1);

        processFile(inputFilePath, outputFilePath, key, encrypt);

        scanner.close();
    }
}
