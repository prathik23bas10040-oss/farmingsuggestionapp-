# farmingsuggestionapp-
import java.util.*;
import java.io.*;
public class FarmingSuggestionApp {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int choice = 0;
        while (choice != 3) {
            System.out.println("\n==== Farming Suggestion System ====");
            System.out.println("1. Get Suggestions");
            System.out.println("2. View Previous Records");
            System.out.println("3. Exit");
            System.out.println("Enter your choice: ");
            choice = sc.nextInt();
            if (choice == 1) {
                getSuggestions(sc);
            } else if (choice == 2) {
                showRecords();
            } else if (choice == 3) {
                System.out.println("Exiting... Goodbye!");
            } else {
                System.out.println("Invalid option! Try again.");
            }
        }
    }
    public static void getSuggestions(Scanner sc) {
        System.out.println("Enter temperature (°C): ");
        int temp = sc.nextInt();
        System.out.println("Enter rainfall (mm): ");
        int rain = sc.nextInt();
        String crop = "";
        String irrigation = "";
        String warning = "";
        if (temp >= 20 && temp <= 30 && rain >= 80 && rain <= 150) {
            crop = "Rice";
        } else if (temp >= 25 && temp <= 35 && rain < 80) {
            crop = "Millets";
        } else if (temp >= 15 && temp <= 25 && rain > 150) {
            crop = "Sugarcane";
        } else if (temp >= 10 && temp <= 20 && rain < 60) {
            crop = "Wheat";
        } else {
            crop = "No perfect crop found";
        }
        if (rain < 50) {
            irrigation = "High irrigation needed";
        } else if (rain < 120) {
            irrigation = "Moderate irrigation needed";
        } else {
            irrigation = "No irrigation needed";
        }
        if (temp > 40) {
            warning += "Heat wave alert! ";
        }
        if (rain > 200) {
            warning += "Heavy rainfall alert! ";
        }
        if (rain < 20) {
            warning += "Drought warning! ";
        }
        System.out.println("\n=== Suggestions ===");
        System.out.println("Crop Suggestion: " + crop);
        System.out.println("Irrigation Suggestion: " + irrigation);
        System.out.println("Warnings: " + (warning.equals("") ? "None" : warning));
        saveRecord(temp, rain, crop, irrigation, warning);
    }
    public static void saveRecord(int temp, int rain, String crop, String irrigation, String warning) {
        try {
            FileWriter fw = new FileWriter("records.txt", true);
            fw.write("Temp: " + temp + ", Rain: " + rain + ", Crop: " + crop + ", Irrigation: " + irrigation + ", Warning: " + warning + "\n");
            fw.close();
            System.out.println("Record saved!");
        } catch (Exception e) {
            System.out.println("Error saving record.");
        }
    }
    public static void showRecords() {
        try {
            File f = new File("records.txt");
            if (!f.exists()) {
                System.out.println("No records found.");
                return;
            }
            Scanner fileReader = new Scanner(f);
            System.out.println("\n=== Past Records ===");
            while (fileReader.hasNextLine()) {
                System.out.println(fileReader.nextLine());
            }
            fileReader.close();
        } catch (Exception e) {
            System.out.println("Error reading file.");
        }
    }
}

