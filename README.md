import java.util.HashMap;
import java.util.Scanner;

public class Translator {
    
    private static HashMap<String, String> dictionary = new HashMap<>();

    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);

        
        dictionary.put("apple", "яблоко");
        dictionary.put("dog", "собака");
        dictionary.put("cat", "кошка");

        while (true) {
            
            System.out.print("Введите слово на английском языке (или 'exit' для выхода): ");
            String word = scanner.nextLine().toLowerCase();

            
            if (word.equals("exit")) {
                System.out.println("Выход из программы.");
                break;
            }

            
            if (dictionary.containsKey(word)) {
                System.out.println("Перевод: " + dictionary.get(word));
            } else {
                System.out.println("Перевод не найден. Введите перевод для слова \"" + word + "\": ");
                String translation = scanner.nextLine();
                // Сохранение перевода в словарь
                dictionary.put(word, translation);
                System.out.println("Слово \"" + word + "\" и его перевод \"" + translation + "\" добавлены в словарь.");
            }
        }

        
        scanner.close();
    }
}
