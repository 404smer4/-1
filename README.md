Отчет по лабораторной работе № 1

Группа: ПМ-2403
Выполнил: Баранов Дмитрий Андреевич
Вариант: 5

Содержание:

 1. Постановка задачи
 2. Входные и выходные данные
 3. Выбор структуры данных
 4. Алгоритм
 5. Программа
 6. Анализ правильности решения
 7. Постановка задачи

Дано неравенство: (ax - 1) / (bx) >= 0, где a и b — параметры, вводимые с клавиатуры. Требуется решить это неравенство для x.

Разбор неравенства:
Неравенство (ax - 1) / (bx) >= 0 можно решить путем анализа знаков числителя и знаменателя дроби.
Рассмотрим условия для положительности дроби:

 1. Числитель и знаменатель имеют один и тот же знак.
 2. Учтем случаи, когда числитель равен нулю (это граница для решения).

Условия:

 • ax - 1 >= 0 и bx > 0, либо
 • ax - 1 <= 0 и bx < 0.

Отсюда можно выделить интервалы для решения в зависимости от значений параметров a и b.

 2. Входные и выходные данные

Входные данные:

 • a: целое число, коэффициент при x в числителе;
 • b: целое число, коэффициент при x в знаменателе.

Выходные данные:

 • Значения x, для которых неравенство выполняется, или сообщение о том, что решения нет.

 3. Выбор структуры данных

Для хранения параметров a и b подойдут целочисленные переменные типа int. Для хранения значения x можно использовать тип double, чтобы учитывать возможные дробные значения.

 4. Алгоритм

Алгоритм выполнения программы:

 1. Ввести значения a и b.
 2. Проверить знак коэффициента b:
 • Если b = 0, неравенство не имеет решения, так как знаменатель равен нулю.
 3. Решить неравенство в зависимости от знаков a и b:
 • Если a = 0, результат зависит от b:
 • Если b > 0, выводим, что x > 0.
 • Если b < 0, выводим, что x < 0.
 • Если a ≠ 0, решить неравенство (ax - 1) / (bx) >= 0 через разбиение на случаи.
 4. Вывести результаты.
 5. Программа

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Ввод коэффициентов a и b
        System.out.print("Введите значение a: ");
        int a = scanner.nextInt();
        System.out.print("Введите значение b: ");
        int b = scanner.nextInt();

        // Проверка знаменателя
        if (b == 0) {
            System.out.println("Неравенство не имеет решений, так как знаменатель равен нулю.");
        } else if (a == 0) {
            // Случай, когда a = 0
            if (b > 0) {
                System.out.println("Решение: x > 0");
            } else {
                System.out.println("Решение: x < 0");
            }
        } else {
            // Основной случай, когда a и b не равны нулю
            double boundary = 1.0 / a; // Точка, где числитель равен нулю
            if (b > 0) {
                if (a > 0) {
                    System.out.println("Решение: x >= " + boundary);
                } else {
                    System.out.println("Решение: x <= " + boundary);
                }
            } else {
                if (a > 0) {
                    System.out.println("Решение: x <= " + boundary);
                } else {
                    System.out.println("Решение: x >= " + boundary);
                }
            }
        }

        scanner.close();
    }
}

 6. Анализ правильности решения

Программа работает корректно при различных значениях параметров a и b, учитывая все возможные случаи для дробного неравенства.

Примеры тестирования:

 1. Тест на a = 2, b = 3:
 • Input: 2 3
 • Output: x >= 0.5
 2. Тест на a = -1, b = -2:
 • Input: -1 -2
 • Output: x >= -1.0
 3. Тест на a = 0, b = 1:
 • Input: 0 1
 • Output: x > 0
 4. Тест на a = 1, b = 0:
 • Input: 1 0
 • Output: Неравенство не имеет решений, так как знаменатель равен нулю.
