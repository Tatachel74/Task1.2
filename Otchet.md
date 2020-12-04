# **Тестирование кода в Idea**
### 
Дата начала тестирования 23.11.2020
###
 Дата окончания тестирования 23.11.2020
### 
На тестирование затрачено 4 часа 
###
 Был применен метод белого ящика, а также техника граничный значений
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
    } а


###
 *В результате тестирования выявлены следующие дефекты*:
#### 
 Запустился код на проверку банковских карт с номерами х4929459591980519,4539335618247151
 в результате проверки этих карт все хорошо. 
####
Затем я проверила другие банковские карты с номерами 4539377861921059088, 372262866155837
 в результате проверки этих карт вылезла ошибка. 
####
[Ошибка в запуске кода с номером карты 4539377861921059088](https://github.com/Tatachel74/Task1.2/issues/1)
####
[Запуск кода в Идея с номером карты 372262866155837 не работает](https://github.com/Tatachel74/Task1.2/issues/2)

# **Программное окружение**
Устройство: windows 8_OC
Браузер: Chrome Версия 85.0.4183.102 (Официальная сборка), (64 бит)
