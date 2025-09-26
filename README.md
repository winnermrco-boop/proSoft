# proSoft
1. Closest Enemy
Задача: Стрелять в ближайшего врага на каждом ходе.

csharp
if (dist1 < dist2)
    Console.WriteLine(enemy1);
else
    Console.WriteLine(enemy2);
Идея: Сравнить расстояния до двух врагов и выбрать ближайшего.

2. Pod Racing
Задача: Управлять космическим кораблём, двигаясь к следующей контрольной точке.

c
printf("%d %d 100\n", next_checkpoint_x, next_checkpoint_y);
Идея: Всегда лететь к координатам следующего чекпоинта на максимальной тяге.

3. Defibrillators
Задача: Найти ближайший дефибриллятор по географическим координатам.

c
double calculateDistance(double lonA, double latA, double lonB, double latB) {
    double x = (lonB_rad - lonA_rad) * cos((latA_rad + latB_rad) / 2.0);
    double y = (latB_rad - latA_rad);
    return sqrt(x*x + y*y) * EARTH_RADIUS;
}
Идея: Использовать формулу гаверсинуса для расчёта расстояния на сфере.

4. Conway's Game of Life
Задача: Реализовать один шаг эволюции клеточного автомата.

cpp
int liveNeighbors = countLiveNeighbors(board, x, y, width, height);
if (board[y][x] == '1') {
    if (liveNeighbors < 2 || liveNeighbors > 3) {
        nextBoard[y][x] = '0';
    }
} else {
    if (liveNeighbors == 3) {
        nextBoard[y][x] = '1';
    }
}
Идея: Для каждой клетки подсчитать живых соседей и применить правила игры.

5. 8 Queens
Задача: Расставить 8 ферзей на шахматной доске так, чтобы они не атаковали друг друга.

cpp
bool isSafe(vector<string>& board, int row, int col) {
    // Проверка строк, столбцов и диагоналей
    for (int i = 1; i < n; i++) {
        if (row-i >= 0 && col-i >= 0 && board[row-i][col-i] == 'Q') return false;
        // ... проверка всех направлений
    }
    return true;
}
Идея: Алгоритм с возвратом (backtracking) с проверкой конфликтов.

6. Zombie Survival Game
Задача: Управлять Эшем для спасения людей от зомби.

cpp
// Стратегия: двигаться к ближайшему зомби
int minDistSq = 16000*16000 + 9000*9000;
for (const auto& zombie : zombies) {
    int distSq = ash.distanceSquaredTo(zombie);
    if (distSq < minDistSq) {
        minDistSq = distSq;
        target = zombie;
    }
}
Идея: Использовать квадрат расстояния для оптимизации, двигаться к ближайшей угрозе.
