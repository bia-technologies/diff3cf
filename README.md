# Утилита для автоматического сравнения переопределенных в расширении модулей измененных в новом релизе поставки основной конфигурации

## Особенности данного решения
- скрипт автоматически сравнивает конфигурации и расширение, выгруженные в формате XML (выгрузка из конфигуратора)
- расширение также должно быть выгружено в формате XML
- помимо стандартных модулей реализована возможность сравнивать обработки заполнения вынесенные из форм документов в обработки
- результат сравнения сохраняется в файл отчет в формате HTML

## Установка

Установка на компьютер стандартна

- склонировать репозиторий или
- распаковать в нужный каталог архив репозитория или
- для Windows запустить [installlocalhost.bat](/installlocalhost.bat)

## Использование
Приложение позволяет сравнивать переопределенные в расширении методы, а также изменение структуры метаданных. Для каждого из этих режимов реализованы соответствующие команды.

Возможные команды:
 help     - Выводит справку по командам
 version  - Выводит версию приложения
 diff     - Выполняет сравнение расширения с основной конфигурацией и новой поставкой
 objects  - Выполняет анализ изменения объектов из основной конфигурации в новой поставке

diff - Выполняет сравнение расширения с основной конфигурацией и новой поставкой
Параметры:
 <КаталогОсновнойКонфигурации> - Каталог основной конфигурации
 <КаталогПоставки> - Каталог поставки
 <КаталогРасширения> - Каталог расширения
 <ФайлРезультат> - Файл-отчет, результат сравнения конфигураций

Перед использованием необходимо выгрузить релиз поставки в формате XML в произвольный каталог

- для сравнения обработок заполнения в свойствах обработки в поле комментарий необходимо указать переопределенный модуль в формате:
    "Adopted.Documents\<Имя документа>\<Путь к модулю>\<ИмяМодуля.bsl>"
    Например: Adopted.Documents\Отгул\Forms\ФормаДокумента\Ext\Form\Module.bsl

- пример вызова для получения анализа переопределенных методов:
    diff3cf diff <каталог основной конфигурации> <каталог с релизом поставки> <каталог с расширением> <файл результат>.html

- пример вызова для получения анализа изменения структуры метаданных:
    diff3cf objects <каталог основной конфигурации> <каталог с релизом поставки> <файл результат>.txt
