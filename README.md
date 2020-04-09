## Отчет о тестировании приложения "Money Transfer"
**С помощью программы IntelliJ IDEA протестировано приложения для перевода денежных средств. Тестирование показало ошибку в операции перевода денежных средств со счета банка на счет клиента. 
На основании кода сделан вывод во неправильном использвании переменной `int`.**

### Цель тестирования - 

проверить соответствие поведения программы с ее требованиями.

### Описание тестирования

 Было проведено функциональное тестирование программы с помощью IntelliJ IDEA. Определен баг в коде, который не позволяет совершать правильные вычисления (перевод денег на карту)

### Результаты тестирования

1. Приложение работает корректно до тех пор, пока сумма не превышает допустимые значения параметра `int` от -2 147 483 648 до 2 147 483 64
2. [Ошибка при переводе денежных средств на карту клиента](https://github.com/baskrasen/javaqa-homeworks-programming-1.2_money-_transfer/issues/1) - ссылка на issue 
### Рекомендации
Использовать переменную `long`  
```java
public class Main {
    public static void main(String[] args) {
        long balance = 2_000_000_000;
        long transaction = 500_000_000;
        long total = transaction + balance;
        System.out.println(total);

    }
}
```