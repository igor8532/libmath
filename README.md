libmath - библиотека с математическими функциями: сложение, вычитание, умножение, деление и возведение в степень.

Сборка без CMake:

Генерируем объектный файл. В корневой директории репозитория с библиотекой выполним команду:
g++ -c src/libmath.cpp -o libmath.o -I./include

Архивируем объектные файлы:
ar rvs libmath.a libmath.o

Скопируем библиотеку и заголовочный файл в системные директории:
sudo cp libmath.a /usr/local/lib/
sudo cp include/libmath.h /usr/local/include/

Сборка проекта с библиотекой:
g++ "исходники" -I/usr/local/include -L/usr/local/lib -lmath -o "имя исполняемого файла"


Сборка с CMake:

Команда на подготовку конфигурации для сборки нашего проекта:
cmake -B build

Сборка проекта:
cmake --build build
(полный аналог командам:
g++ -c src/libmath.cpp -o libmath.o -I./include
ar rvs libmath.a libmath.o)

Установка проекта:
sudo cmake --build build --target install
(аналог командам:
sudo cp libmath.a /usr/local/lib/
sudo cp include/libmath.h /usr/local/include/)
