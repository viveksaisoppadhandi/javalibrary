# javalibrary
import java.util.*;

class Main {
    public static void main(String[] args) {
        Map<String, List<String>> userPrefs = new HashMap<>();
        userPrefs.put("Alice", Arrays.asList("Laptop", "Mouse", "Keyboard"));
        userPrefs.put("Bob", Arrays.asList("Laptop", "Camera"));
        userPrefs.put("Charlie", Arrays.asList("Camera", "Tripod"));

        String targetUser = "Alice";
        Set<String> recommendations = new HashSet<>();

        for (Map.Entry<String, List<String>> entry : userPrefs.entrySet()) {
            if (!entry.getKey().equals(targetUser)) {
                for (String item : entry.getValue()) {
                    if (!userPrefs.get(targetUser).contains(item)) {
                        recommendations.add(item);
                    }
                }
            }
        }

        System.out.println("Recommendations for " + targetUser + ":");
        for (String rec : recommendations) {
            System.out.println("- " + rec);
        }
    }
}
