# Лабораторная работа 2. Скрипты `shell`. Продолжение.

Изучение элементов и конструкций скриптов `shell`: переменных, параметров, ветвлений, циклов, вычислений, команд `shell` и вызовов внешних программ (`shell`, `sed`, `awk`, `wget`,  различные фильтры и т.д.) для решения достаточно сложной задачи, имеющей практическое значение, а также принципов интеграции Unix-программ скриптами `shell`.

## Условие

Создать один или более скриптов `shell`, выполняющих условие вариантов заданий.
При выполнении считать, что размер окна консоли жёстко задан и не может изменяться.
Кроме `bash` можно использовать другие варианты `shell`'ов (`zsh`, `csh` и другие).

## Варианты заданий

1. Хранитель экрана (screensaver) для консоли: большие текстовые часы, меняющие своё расположение на экране.
    Реализовать свой генератор случайных чисел, необходимый для нахождения нового положения часов на экране.
    Основой для генератора может послужить мультипликативный алгоритм генерации (можно выбрать другой, желательно тоже целочисленный).
    Инициализация от текущего времени. Обновление генератора через фиксированные промежутки времени (например, 10 секунд).

2. Клиент для **[pastebin](http://pastebin.com)** (или похожего сервиса).
    Реализовать поддержку следующих функций:

    - создание новой текстовой записи из `stdin` или файла, указанного через аргументы командной строки, автоматического (на основе расширения файла) или ручного (через аргументы командной строки) выбора языка подсветки;

    - создание новой текстовой записи должно возвращать `id`;

    - вывод на консоль или в файл (в зависимости от аргументов) текстовой записи по `id`;

    - для создания и скачивания должен использоваться один и тот же скрипт.

    Пример использования:

    - Создать новую запись с типом текст: `echo testing | ./pastebin.sh -t text`
    - Вывести на экран запись по `id=QEXe0syg`: `./pastebin.sh QEXe0syg`

3. Написать консольную версию игры **[2048](https://gabrielecirulli.github.io/2048/)**. Для сохранения лучших результатов использовать файл. Показывать список лучших результатов в конце игры.

4. Написать консольную версию игры для двоих "Крестики-нолики". Предусмотреть создание скриншота - файла, содержащего текст текущего игрового поля.

5. Реализовать поиск файлов с обходом дерева каталогов.
    Над найденными файлами выполняются заданные действия (похоже на утилиту `find`).

    Требования к поиску:

    - поиск файла по имени, образец поиска может быть регулярным выражением (имена проверяются на соответствие регулярному выражению). Образец передается как аргумент командной строки. Поиск начинается с текущей директории;

    - поиск файла по имени, образец поиска задан списком (имена проверяются на совпадение с любым из этого списка). Способ передачи списка -- ряд аргументов в командной строке. Поиск начинается с текущей директории.

    Действия над найденными файлами:

    - для файлов с заданным заголовком (первой строкой) вывод их содержимого в виде листинга: построчно, строки пронумерованы. Заголовок считается фиксированным. 

6. Поиск файлов аналогично предыдущему заданию, отличаются действия над найденными файлами:

    - подсчет суммы значений байтов каждого файла и общей по всем файлам (подсчет контрольной суммы файлов). Вместо суммирования можно использовать другую доступную функцию.

## Ресурсы

- https://wiki.ubuntu.com/ChangingShells
