public class USEcase7 {

    /**
     * Inner Static Class that stores
     * character and its banner pattern
     */
    static class CharacterPatternMap {

        private char character;
        private String[] pattern;

        /**
         * Constructor to initialize character and pattern
         * 
         * @param character Character value
         * @param pattern   7-line banner pattern
         */
        public CharacterPatternMap(char character, String[] pattern) {
            this.character = character;
            this.pattern = pattern;
        }

        /**
         * Returns the character
         * 
         * @return character
         */
        public char getCharacter() {
            return character;
        }

        /**
         * Returns the banner pattern
         * 
         * @return pattern array
         */
        public String[] getPattern() {
            return pattern;
        }
    }


    /**
     * Returns CharacterPatternMap object for a character
     */
    public static CharacterPatternMap getCharacterPattern(char ch) {

        if (ch == 'O') {
            return new CharacterPatternMap('O', new String[]{
                    " ***** ",
                    "*     *",
                    "*     *",
                    "*     *",
                    "*     *",
                    "*     *",
                    " ***** "
            });
        }

        if (ch == 'P') {
            return new CharacterPatternMap('P', new String[]{
                    "****** ",
                    "*     *",
                    "*     *",
                    "****** ",
                    "*      ",
                    "*      ",
                    "*      "
            });
        }

        if (ch == 'S') {
            return new CharacterPatternMap('S', new String[]{
                    " ***** ",
                    "*      ",
                    "*      ",
                    " ***** ",
                    "      *",
                    "      *",
                    " ***** "
            });
        }

        return null;
    }


    /**
     * Prints banner word using StringBuilder
     */
    public static void printBanner(String word) {

        StringBuilder[] lines = new StringBuilder[7];

        for (int i = 0; i < 7; i++) {
            lines[i] = new StringBuilder();
        }

        for (int i = 0; i < word.length(); i++) {

            CharacterPatternMap map =
                    getCharacterPattern(word.charAt(i));

            String[] pattern = map.getPattern();

            for (int j = 0; j < 7; j++) {
                lines[j].append(pattern[j]).append("  ");
            }
        }

        for (int i = 0; i < 7; i++) {
            System.out.println(lines[i]);
        }
    }


    /**
     * Main Method
     */
    public static void main(String[] args) {

        printBanner("OOPS");

    }
}