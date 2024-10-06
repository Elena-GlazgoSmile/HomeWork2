# АНАЛИЗ ДАННЫХ В РАЗРАБОТКЕ ИГР [in GameDev]
Отчет по лабораторной работе #2 выполнил(а):
- Власова Елена Васильевна
- РИ230931
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Выберать одну из игровых переменных в игре СПАСТИ РТФ: Выживание (HP, SP, игровая валюта, здоровье и т.д.), описать её роль в игре, условия изменения / появления и диапазон допустимых значений. Построить схему экономической модели в игре и укажите место выбранного ресурса в ней.
- Задание 2.
- Заполнить google-таблицу данными, описывающими выбранную игровую переменную в игре “СПАСТИ РТФ:Выживание”
- Задание 3.
- Настроить на сцене Unity воспроизведение звуковых файлов, описывающих динамику изменения выбранной переменной.
- Выводы.
- ✨Magic ✨

## Цель работы
Научиться передавать в Unity данные из Google Sheets с помощью Python.

## Задание 1
### Выберите одну из игровых переменных в игре СПАСТИ РТФ: Выживание (HP, SP, игровая валюта, здоровье и т.д.), опишите её роль в игре, условия изменения / появления и диапазон допустимых значений. Постройте схему экономической модели в игре и укажите место выбранного ресурса в ней.
Ход работы:
- Я выбрала такую переменную, как здоровье, потому что это святая-святых для любого персонажа в аркадах. Это тот ресурс, за которым игрок должен неустанно следить и хранить, как зеницу ока. Ведь от того, насколько долго игрок сможет сохранить здоровье, настолько будет продолжаться игра. То есть пока есть здоровье, игра будет продолжаться.
- Прежде всего, с самого начала игры каждый игрок получает одинаковое количество здоровья - 30. В моей экономической модели этот пункт называется исходное здоровье. На этапе начала игры все игроки равны и никто до начала игры не может намеренно увеличить или уменьшить данные, которые прописаны самими создателями игры.
- Однако здоровье надо где-то хранить, и логичнее всего хранить здоровье в шкале. Шкала здоровья - ядро экономической модели, которую я построила. Шкала помогает пользователю тем, что он может видеть, сколько здоровья у него осталось + шкала задаёт диапозон здоровья, в моей экономической модели здоровье колеблется от 0 до 30. Этот диапозон помогает с одной стороны при увеличении уровня не дать игроку увеличить здоровье до + бесконечности (какой бы тогда был смысл, если нам не страшен никакой урон?), а с другой стороны помогает игроку почувствовать, что если он не будет следить за этой шкалой, то игра может и резко закончиться, как только шкала дойдёт до 0.
- На картинке Вы можете видеть экономическую модель, которую я сама нарисовала.

![Component 2 (16)](https://github.com/user-attachments/assets/4e48c964-5b80-4443-bdf5-2ab3bdc27cdc)



## Задание 2
### Должна ли величина loss стремиться к нулю при изменении исходных данных? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ.

- Перечисленные в этом туториале действия могут быть выполнены запуском на исполнение скрипт-файла, доступного [в репозитории](https://github.com/Den1sovDm1triy/hfss-scripting/blob/main/ScreatingSphereInAEDT.py).
- Для запуска скрипт-файла откройте Ansys Electronics Desktop. Перейдите во вкладку [Automation] - [Run Script] - [Выберите файл с именем ScreatingSphereInAEDT.py из репозитория].

```py

import ScriptEnv
ScriptEnv.Initialize("Ansoft.ElectronicsDesktop")
oDesktop.RestoreWindow()
oProject = oDesktop.NewProject()
oProject.Rename("C:/Users/denisov.dv/Documents/Ansoft/SphereDIffraction.aedt", True)
oProject.InsertDesign("HFSS", "HFSSDesign1", "HFSS Terminal Network", "")
oDesign = oProject.SetActiveDesign("HFSSDesign1")
oEditor = oDesign.SetActiveEditor("3D Modeler")
oEditor.CreateSphere(
	[
		"NAME:SphereParameters",
		"XCenter:="		, "0mm",
		"YCenter:="		, "0mm",
		"ZCenter:="		, "0mm",
		"Radius:="		, "1.0770329614269mm"
	], 
)

```

## Задание 3
### Какова роль параметра Lr? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ. В качестве эксперимента можете изменить значение параметра.

- Перечисленные в этом туториале действия могут быть выполнены запуском на исполнение скрипт-файла, доступного [в репозитории](https://github.com/Den1sovDm1triy/hfss-scripting/blob/main/ScreatingSphereInAEDT.py).
- Для запуска скрипт-файла откройте Ansys Electronics Desktop. Перейдите во вкладку [Automation] - [Run Script] - [Выберите файл с именем ScreatingSphereInAEDT.py из репозитория].

```py

import ScriptEnv
ScriptEnv.Initialize("Ansoft.ElectronicsDesktop")
oDesktop.RestoreWindow()
oProject = oDesktop.NewProject()
oProject.Rename("C:/Users/denisov.dv/Documents/Ansoft/SphereDIffraction.aedt", True)
oProject.InsertDesign("HFSS", "HFSSDesign1", "HFSS Terminal Network", "")
oDesign = oProject.SetActiveDesign("HFSSDesign1")
oEditor = oDesign.SetActiveEditor("3D Modeler")
oEditor.CreateSphere(
	[
		"NAME:SphereParameters",
		"XCenter:="		, "0mm",
		"YCenter:="		, "0mm",
		"ZCenter:="		, "0mm",
		"Radius:="		, "1.0770329614269mm"
	], 
)

```

## Выводы

Абзац умных слов о том, что было сделано и что было узнано.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
