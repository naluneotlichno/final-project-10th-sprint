# 🚀 Bash Automation Script – Автоматизация файловых операций

## 📌 Описание скрипта
Этот Bash-скрипт демонстрирует **автоматизацию работы с файловой системой**, создание и управление каталогами, работу с переменными окружения, редактирование файлов и выполнение команд. Скрипт подходит для изучения **основ Bash**, файловых операций и обработки данных в Linux.

## 🔥 **Функциональность**
✅ **Создание структуры каталогов** (`task` с вложенными `dir1`, `dir2`, `dir3/dir4`)  
✅ **Создание и редактирование файлов** (пустые файлы, скрипты, текстовые файлы)  
✅ **Управление правами доступа** (`chmod 764` для исполняемого скрипта)  
✅ **Копирование и перемещение файлов** (`cp -r`, `mv`)  
✅ **Поиск и фильтрация файлов** (`find`, `grep`, `sort`)  
✅ **Работа с переменными окружения** (`export NAME="Всем студентам"`)  
✅ **Запуск Bash-скрипта с аргументами** (`hello.sh "$NAME"`)  
✅ **Удаление каталогов и файлов** (`rm -rf task`)  

## 🛠 **Как запустить скрипт?**

### **🔹 1. Сохраните скрипт в файл**
Создайте файл `script.sh` и вставьте код.
```sh
nano script.sh
```

### **🔹 2. Дайте скрипту права на выполнение**
```sh
chmod +x script.sh
```

### **🔹 3. Запустите скрипт**
```sh
./script.sh
```

## 📂 **Структура каталогов после выполнения**
После выполнения скрипта создаётся следующая файловая структура:
```
task/
├── dir1/
│   ├── summary.txt  (перемещён в "Практическое задание")
├── dir2/
│   ├── empty
│   ├── hello.sh (скрипт с приветствием)
│   ├── list.txt (список файлов)
├── dir3/
│   ├── dir4/
│       ├── empty (копия из dir2)
│       ├── hello.sh (копия из dir2)
│       ├── list.txt (копия из dir2)
├── "Практическое задание" (итоговый файл со всеми операциями)
```

## 📝 **Разбор ключевых операций**

### **1️⃣ Создание файлов и директорий**
```sh
mkdir -p task/dir1 task/dir2 task/dir3/dir4
cd task
touch dir2/empty
```
Создаётся структура каталогов и пустой файл `empty`.

### **2️⃣ Запись и выполнение Bash-скрипта**
```sh
echo '#!/bin/bash' > dir2/hello.sh
echo 'echo "$1, привет!"' >> dir2/hello.sh
chmod 764 dir2/hello.sh
```
Создаётся исполняемый файл `hello.sh`, который принимает аргумент и выводит приветствие.

### **3️⃣ Работа с переменной окружения**
```sh
export NAME="Всем студентам"
./dir2/hello.sh "$NAME" >> dir1/summary.txt
```
Создаётся переменная `NAME`, которая передаётся в `hello.sh`, а результат записывается в `summary.txt`.

### **4️⃣ Поиск и фильтрация данных**
```sh
find . -name "*.txt" > dir1/summary.txt
cat dir2/list.txt >> dir1/summary.txt
grep "dir" "Практическое задание" | sort
```
Формируется список `.txt` файлов, записывается в `summary.txt`, затем фильтруются и сортируются строки с `dir`.

### **5️⃣ Удаление директории и файлов**
```sh
rm -rf task
```
Полное удаление каталога `task` после выполнения всех операций.

