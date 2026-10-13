#include <iostream>
#include <string>
#include <vector>

int main() {
    const int NUM_LINES = 5;
    const int NUM_VALUES = 4;  // можно менять от 3 до 5
    const int REPEATS = 3;

    std::vector<std::string> lines(NUM_LINES);

    // Ввод 5 строк
    std::cout << "Введите " << NUM_LINES << " строк:\n";
    for (int i = 0; i < NUM_LINES; ++i) {
        std::cout << "Строка " << (i + 1) << ": ";
        std::getline(std::cin, lines[i]);
    }

    // Ввод 3-5 значений
    std::vector<std::string> values(NUM_VALUES);
    std::cout << "\nВведите " << NUM_VALUES << " значений:\n";
    for (int i = 0; i < NUM_VALUES; ++i) {
        std::cout << "Значение " << (i + 1) << ": ";
        std::getline(std::cin, values[i]);
    }

    // Дублируем 5 строк 3 раза
    std::cout << "\n=== Результат ===\n";
    for (int r = 0; r < REPEATS; ++r) {
        std::cout << "\n--- Повтор " << (r + 1) << " ---\n";

        for (int i = 0; i < NUM_LINES; ++i) {
            std::cout << lines[i];

            // Подставляем значения в конец каждой строки
            for (int v = 0; v < NUM_VALUES; ++v) {
                std::cout << " " << values[v];
            }
            std::cout << "\n";
        }
    }

    return 0;
}
