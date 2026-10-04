 ЗВІТ ДО ЛАБОРАТОРНОЇ РОБОТИ №3
з дисципліни: «Операційні системи»  
Тема: Знайомство з базовими командами CLI-режиму в Linux  
Мета:  
 1. Ознайомитися з базовими командами CLI-режиму в Linux.
 2. Ознайомитися з базовими текстовими командами термінала в різних ОС.

1.Словник англійських термінів 

CLI (Command Line Interface) — A text-based user interface used to view and manage computer files and execute commands.

Shell — A command-line interpreter that translates user-entered text commands into instructions for the operating system kernel.

Bash (Bourne Again Shell) — The default command-line shell and script language for most Linux distributions.

Prompt— A sequence of characters displayed on a command line to indicate that the shell is ready to accept input.

Command — An executable program or built-in directive given to the computer to perform a specific task.

Option (Flag) — A parameter passed to a command (usually preceded by `-` or `--`) to modify its standard behavior.

Argument — The target or data (such as a filename or path) upon which a command operates.

Variable — A named storage location in memory used by the shell to retain data and system configuration state.

Environment Variable** — A dynamic variable that affects the behavior of processes and shell sessions across the operating system.

Alias — A user-defined shortcut or custom nickname used to execute a longer command sequence.

Quote (Quoting) — Characters (`"`, `'`, `` ` ``) used to control how the shell interprets special characters, whitespace, and expansion.

Control Statements — Operators (`;`, `&&`, `||`) used to control the execution order and condition of multiple commands.

2.Завдання для попередньої підготовки

 2.1. Визначення основних поняття
Командний інтерпретатор — це програма, яка зчитує введений користувачем текст, розпізнає команди та передає їх на виконання операційній системі.

Оболонка (Shell) — середовище-посередник між користувачем і ядром ОС, що надає інтерфейс командного рядка (CLI) або графічний інтерфейс (GUI).

Команда — виконуваний файл або вбудована у Shell інструкція, яка змушує комп'ютер виконати визначену дію.

 2.2. Відповіді на питання підготовки
1. Інформація у рядку запрошення (prompt):  
   У замовчуваній формі на кшталт `sysadmin@localhost:~$` показується:
   * Ім'я користувача (`sysadmin`).
   * Назва ПК/хоста (`localhost`).
   * Поточна робоча папка (`~` — домашній каталог `/home/sysadmin`).
   * Символ привілеїв (`$` — звичайний юзер, `#` — root).

2. Навіщо потрібні параметри та аргументи:
   Параметри (options) змінюють режим роботи команди (наприклад, вивід у довгому форматі чи відображення прихованих файлів).
   Аргументи вказують, до якого саме об'єкта (файлу або папки) застосовується команда.

3. Призначення команди `ls` та приклади:  
   Призначена для перегляду вмісту каталогів.
   * `ls -a /home` — виводить всі файли, в тому числі приховані.
   * `ls -lh /var/log` — показує файли у довгому форматі з розмірами у зручному вигляду (КБ, МБ).
   * `ls -lt /etc` — сортує файли у `/etc` за часом останньої зміни.

4. Використання історії команд:  
   Історія (`history`) дозволяє повертатися до раніше введених команд стрілками Вгору/Вниз або комбінацією `Ctrl + R`. Це значно зекономить час на повторний ввід довгих команд.

5. Призначення команди `echo`:  
   Виводить текстовий рядок або значення змінної у термінал.

6. Змінні в Bash: 
   Збережені значення у пам'яті. Бувають:
   Локальні — діють тільки в поточному вікні/сесії Bash.
   Змінні оточення (Environment)** — доступні для всіх дочірніх програм та процесів у цій сесії.

7. Команди `env`, `export`, `unset`: 
   * `env` — виводить усі змінні оточення.
   * `export` — робить локальну змінну змінною оточення.
   * `unset` — видаляє змінну з пам'яті.

8. Довідкові команди:
   `man <команда>`, `<команда> --help`, `help <вбудована_команда>`, `info`.

3.Хід роботи

3.1. Таблиця команд

| Назва команди | Призначення та функціональність |
| :--- | :--- |
| `ls` | Перегляд вмісту поточного каталогу. |
| `ls -l` | Перегляд файлів у довгому форматі (права, власник, розмір, дата). |
| `ls -l /tmp` | Детальний вивід вмісту папки `/tmp`. |
| `type` | Показує тип команди (вбудована, зовнішній файл чи аліас). |
| `which` | Показує шлях до виконуваного файлу зовнішньої команди. |
| `help` | Вбудована довідка для внутрішніх команд Bash. |
| `man` | Відкриває повне системне керівництво (manual page). |
| `echo` | Виводить рядок тексту чи значення змінної. |
| `history` | Виводить список раніше введених команд. |
| `alias` | Створює псевдонім (коротку назву) для довгої команди. |
| `unalias` | Видаляє створений псевдонім. |
| `export` | Передає змінну в оточення дочірніх процесів. |
| `unset` | Видаляє змінну чи функцію з пам'яті. |
| `uname` | Показує інформацію про ядро та ОС. |

3.2. Виконання практичних завдань у терміналі

![Image alt](https://github.com/aleksor233-cloud/LABS/blob/main/Screenshot%202026-10-04%20150403.png)

я не зміг нормально зробити календар в гит баш ,
тому що він не знаходить таку команду і тому зробив як зміг.

5. Відповіді на контрольні запитання
Типи команд у Bash:

Aliases (аліаси) — псевдоніми команд.

Functions (функції) — групи команд у пам'яті.

Built-in (вбудовані) — інтегровані в сам Bash (cd, echo, pwd).

Executable programs (зовнішні) — окремі файли у файловій системі (/bin/ls).

Змінні оточення:

Глобальні змінні, доступні для всіх програм у сесії ($PATH, $USER, $HOME). Переглядаються за допомогою env або export -p.

Змінна $PS1:

Задає формат і вигляд рядка запрошення термінала. Перегляд: echo $PS1.

Зміна $PS1:

Тимчасово змінюється присвоєнням: PS1="new_prompt> ". Рядок запрошення відразу зміниться. Щоб зберегти назавжди, запис export PS1="..." додається у файл ~/.bashrc.

Використання лапок у Bash:

Подвійні " — зберігають пробіли, але розкривають змінні ($VAR) та команди ($(cmd)).

Одинарні ' — сприймають усе всередині як чистий текст (блокують екранування).

Зворотні ` чи $(...) — виконують команду всередині й підставляють її результат.

Інструкції керування:

Об'єднують декілька команд:

; — виконує команди послідовно.

&& — виконує другу команду тільки у разі успіху першої.

|| — виконує другу команду тільки у разі помилки першої.

Різниця між $ та # в кінці запрошення:

$ — звичайний користувач.

# — суперкористувач (root).

Різниця між whereis та locate:

whereis шукає виконувані файли, вихідний код і man-сторінки в системних каталогах у реальному часі.

locate шукає будь-які файли по всій системі за власною кешованою базою даних (працює миттєво, але потребує оновлення бази через updatedb).

6. Висновки

During the completion of Laboratory Work No. 3, we successfully gained practical skills in working with the Linux Command Line Interface (CLI). We studied the key principles of Bash shell operation, including command structures, options, arguments, variables, and aliases. Furthermore, we implemented functions, practiced control statements, and analyzed quote types for command string manipulation. The submission was collaboratively created and tracked within a public Git repository, demonstrating team version control workflow.
EOF
