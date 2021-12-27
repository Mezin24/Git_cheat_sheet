# Git Basic Comands

### **1 Установка**

**git config user.name**
**git config user.name** - проверка имя и мэил пользователя

**git config --global user.name**
**git config --global user.name** -установка

---

### **2 Установка и инициализация**

**git init** -инициализация
rm -rf .git -удаление репозитория

**git add file1.txt file2.txt** -добавление файлов в отслеживание  
**git commit -m 'Commit name'** -комит

**git add file3.txt**  
**git restore --stage <fileName>** - убирает фаил из состояния stage
**git commit --amend** -добавить ФАИЛ в предыдущий коммит

**git commit -a -m 'newCommitName'** - !!! добавляет и создает новый коммит

---

### **3. BRANCH**

**git branch** -показывает имеющиеся векти  
**git branch -v** -список веток с последними коммитами  
**git branch <new brancName>** -СОЗДАНИЕ новую ветку безе перехода в нее

**git switch <secondBrancName>** - !!! ПЕРЕКЛЮЧЕНИЕ переходим на другую ветку (NEW COMMAND)  
**git checkout <secondBrancName>** - переходим на другую ветку (OLD COMMAND)

**git switch -c <newBranchName>** - !!! shortcut создать новую ветку и перейти сразу в нее  
**git checkout -b <newBranchName>** - !!! shortcut создать новую ветку и перейти сразу в нее

**git branch -d <branchName>** - УДАЛЕНИЕ ветки, первоначально перейти в другую ветку. далее подтверждение  
**git branch -D <branchName>** -удаление всей ветки

**git branch -m <newBranchName>** - ПЕРЕИМЕНОВАНИЕ ВЕТКИ, первоначально надо зайти в желаемую ветку

---

### **4. MERGE**

#### (FAST FORWARD MERGE)

**git switch master** - переходим в ветку к которой хотим сделать слияние  
**git merge <branchName>** -сливаем две ветки на основе master branch

---

### **5. DIFF**

**git diff** - сравнить изменения между последним комитом и рабочей областью, показывает unstage changes  
**git diff HEAD** - сравнить все изменения с положением HEAD, показывает unstage changes и stage changes  
**git diff HEAD <fileName>** - в конкретном файле

**git dig --staged <fileName> **- в конкретном файле

**git diff branch1 branch2** -разница между ветками  
**git diff commit1 commit2** -разница между commit

---

### **6. STASHING**

**git stash** - позволяет сохранить незакомиченные изменения stashed and unstashed, заносятся в память stash

**git stash pop** - вставить изменения (извлекаются и удаляются из памяти stash)  
**git stash apply**- вставить изменения (извлекаются и НЕ удаляются из памяти stash)

**git stash lish** - выводит все текущие сохранения в stash  
**git stash apply stash@{2}** - вставить из stash с id 2  
**git stash drop stash@{2}** - удалить из stash с id 2  
**git stash clear** - очистить stash

---

### **7. TIME TRAVELING**

**git checkout <7numbers of commit hash>** - переходим к коммиту с данным номером  
 **git checkout HEAD~1** - переходим на 1 комиит назад  
 **git checkout HEAD~2** - переходим на 2 комиит назад  
 **git switch** - - возвращает к прежней ветке

**git checkout HEAD <file>** - возвращемся к последнему комиту, все изменения в файле пропадают
то же самое  
**git checkout -- <file>**  
**git restore <file>**

**git restore --sourse HEAD~1 <file>** -остаемся в том же рабочем месте но фаил становится как в комите

**git reset <commit-hash>** -удаление всех коммитов до этого, но изменения в файлах остаются, если хотим отменить то применям git restore  
**git reset HEAD~1**
**git reset --hard <commit>** -удаляет все коммиты и все изменения

**git revert <commit>** - создает новый коммит и удаляет все изменения из commit

---

---

## **GITHUB**

**git clone <url>** - копировать репозиторий на комппьютер

**git remote -v** - посмотреть названия remote

**git branch -r** - посмотреть имеющиеся ветки с удаленной веткой  
**git chtckout <origin/main>** - перейти обратно к моменту клонирования  
**git switch <brancName>** - перейдет к удаленной ветке и создаст ее на рабочем компьтере

**git fetch <origin/master>** - мы работаем с клоном и хотим посмотреть изменения в ветке на гитхабе и не испортить текущую работу  
**git fetch <origin> <branch>** - отдельную ветку
