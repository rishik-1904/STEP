public class USEcase5 {

    public static void main(String[] args) {

        // Inline initialization using String.join()
        String[] lines = {

            String.join("   "," *** "," *** ","**** "," ****"),
            String.join("   ","*   *","*   *","*   *","*    "),
            String.join("   ","*   *","*   *","*   *"," *** "),
            String.join("   ","*   *","*   *","**** ","  ***"),
            String.join("   ","*   *","*   *","*    ","    *"),
            String.join("   ","*   *","*   *","*    ","*   *"),
            String.join("   "," *** "," *** ","*    ","**** ")
        };

        // For-each loop to print banner
        for (String line : lines) {
            System.out.println(line);
        }
    }
}