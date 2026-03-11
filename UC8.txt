import java.util.HashMap;

public class USEcase8 {

    /**
     * Creates a HashMap containing ASCII art patterns
     * for supported characters.
     *
     * Each character is mapped to an array of strings,
     * where each string represents one line of the pattern.
     */
    public static HashMap<Character, String[]> createCharacterMap() {

        HashMap<Character, String[]> charMap = new HashMap<>();

        // Pattern for 'O'
        charMap.put('O', new String[]{
                " *** ",
                "*   *",
                "*   *",
                "*   *",
                " *** "
        });

        // Pattern for 'P'
        charMap.put('P', new String[]{
                "**** ",
                "*   *",
                "**** ",
                "*    ",
                "*    "
        });

        // Pattern for 'S'
        charMap.put('S', new String[]{
                " ****",
                "*    ",
                " *** ",
                "    *",
                "**** "
        });

        return charMap;
    }


    /**
     * Displays banner message using character map
     */
    public static void displayBanner(String message,
                                     HashMap<Character, String[]> charMap) {

        int patternHeight = charMap.get('O').length;

        // Loop through rows
        for (int line = 0; line < patternHeight; line++) {

            StringBuilder sb = new StringBuilder();

            // Loop through characters
            for (char ch : message.toCharArray()) {

                String[] pattern = charMap.get(ch);

                sb.append(pattern[line]);
                sb.append("   ");   // Space between letters
            }

            System.out.println(sb.toString());
        }
    }


    /**
     * Main Method
     */
    public static void main(String[] args) {

        HashMap<Character, String[]> charMap =
                createCharacterMap();

        String message = "OOPS";

        displayBanner(message, charMap);
    }
}