# Техническое задание
## Разработка проекта “Игра Жизнь”
## ОПИСАНИЕ ПРОЕКТА
Игра «Жизнь» — клеточный автомат, придуманный английским математиком Джоном Конвеем в 1970 году. Это “игра без игроков”, в которой задаётся начальное состояние “тел”, а игрок лишь наблюдает за её развитием. 
### Правила игры
Место действия игры — размеченная на клетки плоскость, которая может быть безграничной, ограниченной или замкнутой.
Каждая клетка на этой поверхности имеет восемь соседей, окружающих её, и может находиться в двух состояниях: быть «живой» (заполненной) или «мёртвой» (пустой).
Распределение живых клеток в начале игры называется первым поколением. Каждое следующее поколение рассчитывается на основе предыдущего по таким правилам:
1. В пустой (мёртвой) клетке, с которой соседствуют три живые клетки, зарождается жизнь;
2. Если у живой клетки есть две или три живые соседки, то эта клетка продолжает жить; в противном случае (если живых соседей меньше двух или больше трёх) клетка умирает («от одиночества» или «от перенаселённости»).
Игра прекращается, если
1. На поле не останется ни одной «живой» клетки;
2. Конфигурация на очередном шаге в точности (без сдвигов и поворотов) повторит себя же на одном из более ранних шагов (складывается периодическая конфигурация)
3. При очередном шаге ни одна из клеток не меняет своего состояния (частный случай предыдущего правила, складывается стабильная конфигурация). Программа генерирует начальную конфигурацию «живых» клеток, которые затем изменяются согласно правилам. Несмотря на простоту правил, в игре может возникать огромное разнообразие форм.

### Требования к проекту
#### Системные требования
Разработка приложения проходит с использованием языка С++, в качестве системы сборки использована GNU Make, система контроля версий – Git. Программа разрабатывается под операционные системы Linux и macOS.

#### Требования к функциональным характеристикам 
Приложение будет запускаться в консольном окне, в виде живых клеток использован символ – “#”, в виде не живых - пустота.
В данном приложении алгоритм «смены поколения» последовательно просматривает все клетки поля, для каждой подсчитывает соседей, определяя судьбу клетки в новом поколении (не изменится, умрёт, родится). Такой алгоритм использует два двумерных массива — для текущего и для следующего поколений. Начальное состояние клеток задаётся случайным образом или из текстового файла с расширением ".txt". 

### Этапы разработки:
1. Изучение правил игры жизнь и определение основных элементов игры.
2. Разработка алгоритма создания поля и заполнения его сущностями.
3. Разработка правил определения сущностей на игровом поле и определение условий их смерти или выживания.
4. Разработка алгоритма обработки игрового поля и вывода результатов игры.
5. Тестирование и отладка программы.

### Запуск и работа с программой
После запуска исполняемого файла будет открыто консольное окно, в котором появится инструкция к дальнейшей работе с программой. В данном окне пользователь сможет выбрать каким способом будет проходить начальное заполнение окна символами (случайным образом или из текстового файла), также он может завершить программу. После того, как пользователь сделает выбор между вариантами ввода, начнётся выполнение программы. Спустя 30 секунд в консоле появится сообщение с вопросом хочет ли пользователь продолжить выполнение пpограммы, выйти в меню или завершить программу. В зависимости от выбора программа продолжит выполняться и через 30 секунд также приостановится, завершится процесс игры с дальнейшим переходом на начальный экран с выбором варианта ввода или произойдёт завершение программы. Если пользователь допустит ошибку в вводе значений при работе с программой, выведется сообщение об ошибке и будет предложено повторить ввод.
