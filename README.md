# Шпаргалка по работе с Git

## Создание локального Git-репозитория

1. Создать папку проекта:

```mkdir directory
```
2. Сделать папку репозиторием:

```cd ~/dev/directory
   git init
```
## Работа с локальным репозиторием

### Удаление репозитория

```cd ~/dev/directory
   rm -rf .git
```
### Проверка состояния репозитория

```git status
```
### Добавление файлов в локальный репозиторий
1. Создание файлов: 

```touch <file>
```
2. Подготовка к сохраненю:

```git add --all
```
или 

```git add .
```
3. Сохранение:

```git commit -m 'remark' 
```
4. Просмотр истории коммитов

```git log
```
## Создание репозитория на GitHub (удаленного)

1. Зайти на страницу своего профиля в GitHub.
2. Перейти на вкладку *Repositories*.
3. нажать зеленую кнопку *New*.
4. В окне создания репозитория ввести название (удобнее использовать имя локального Git-репозитория).
5. Нажать зеленую кнопку *Create repository*.

## Связывание локального и удаленного репозитория

1. На странице удаленного репозитория выбрать *SSH*  и скопировать URL.
2. Запустить терминал и перейти в каталог локального репозитория:

```cd ~/dev/directory
```
3. Связать репозитории:

```git remote add origin <SSH>
```
4. Убедиться, что репозитории связаны:

```git remote -v
```
## Синхронизирование локального и удаленного репозитория

1. Отправить изменения на удаленный репозиторий:

```git push -u origin main
```
2. Зайти в репозиторий на GitHub и посмотреть изменения.

В дальнейшем, при работе с удаленным репозиторием, флаг -u можно опустить.

## Статусы файлов в Git
untracked - неотслеживаемые файлы; за их изменениями Git не следит.
tracked - файлы, за иизменениями которых Git следит.

Жизненный цикл файлов в Git

```mermaid
graph LR;
  untracked -- "git add" --> staged;
  staged    -- "git commit"  --> tracked/comitted;

  tracked -- "изменения" --> modified;
  modified    -- git add" --> staged;
  staged    -- "git commit"  --> tracked/comitted;

``` 
