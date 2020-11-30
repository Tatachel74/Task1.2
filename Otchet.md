# **Тестирование кода в Idea**
### Дата начала тестирования 23.11.2020
### Дата окончания тестирования 24.11.2020
### На тестирование затрачено 4 часа 
### Был применен метод белого ящика, а также техника граничный значений
### Тестирование кода в idea
# **Описание**
Был произведен запуск кода в Idea
 public class Main {
        public static void main(String[] args) {
            // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
            String number = "372262866155837";
            System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
        }

        public static boolean isValidCardNumber(String number) {
            if (number == null) {
                return false;
            }

            if (number.length() != 16) {
                return false;
            }

            long result = 0;
            for (int i = 0; i < number.length(); i++) {
                int digit;
                try {
                    digit = Integer.parseInt(number.charAt(i) + "");
                } catch (NumberFormatException e) {
                    return false;
                }

                if (i % 2 == 0) {
                    digit *= 2;
                    if (digit > 9) {
                        digit -= 9;
                    }
                }
                result += digit;
            }

            return (result != 0) && (result % 10 == 0);
        }
    } 



### Проверка таких номеров 4929459591980519,4539335618247151
 Result is OK
### Проверка таких номеров 4539377861921059088,372262866155837
Result is FAIL

# **Программное окружение**
Устройство: windows 8_OC
Браузер: Chrome Версия 85.0.4183.102 (Официальная сборка), (64 бит)
