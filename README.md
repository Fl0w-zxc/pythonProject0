|9.1|

Проект был организован — созданы основные пакеты: src — для исходного кода, tests — для тестов.
Инструменты для проверки качества кода (Flake8, black, isort, mypy) были установлены в группу lint через Poetry.
Файл .flake8 был настроен для конфигурации линтера Flake8.
Конфигурации для black, isort и mypy были добавлены в файл pyproject.toml.
В пакете src был создан модуль с названием masks.
В этом модуле были реализованы две функции:
Функция маскировки номера банковской карты get_mask_card_number.
Функция маскировки номера банковского счета get_mask_account.
Линтер Flake8 был запущен для проверки стиля кода.
Black и isort были использованы для форматирования кода.
Статический анализ типов был проведен с помощью mypy, чтобы убедиться в отсутствии ошибок типизации в коде.

---

|9.2|

Новый локальный Git-репозиторий был инициализирован в папке проекта с помощью команды git init.
Файл .gitignore был создан в корне проекта. В него добавлены стандартные шаблоны для Python, чтобы исключить системные и временные файлы, такие как idea и другие.
В процессе разработки кода было сделано минимум три коммита, фиксирующих основные этапы создания проекта:
• Первый коммит зафиксировал прогресс по прошлой домашке. • Второй коммит добавил новые функции. • Третий коммит включил финальные изменения и доработки.
В пакете src был создан новый модуль с именем widget. Этот модуль содержит функции для работы с новыми возможностями приложения.
В модуле widget была создана функция mask_account_card , которая умеет обрабатывать информацию как о картах, так и о счетах. Функция:
• Принимает один аргумент - строку, содержащую тип и номер карты или счета. • Возвращает строку с замаскированным номером. Для карт и счетов используются разные типы маскировки. Существующие функции маскировки из проекта были переиспользованы для избежания дублирования кода.
В том же модуле была создана функция get_date, которая принимает на вход строку с датой в формате "2024-03-11Т02:26:18.671407" и возвращает строку с датой в формате "ДД.ММ.ГГГГ" (например, "11.03.2024").

---

|10.1|

Новые ветки были созданы в репозитории для работы по GitFlow. Основные ветки, такие Kak main, develop, а также feature-ветки для разработки новых функций, были успешно созданы и используются.
Новый репозиторий был создан на GitHub для хранения и совместной работы над проектом.
Содержимое локального репозитория было загружено в созданный репозиторий на GitHub с использованием команд git add, git commit и git push.
В директории src проекта был создан модуль processing, который содержит новые функции для обработки данных.
В модуле processing была написана функция filter_by_state. Она принимает список словарей и опциональное значение для ключа state (по умолчанию "EXECUTED"). Функция возвращает новый список словарей, содержащий только те элементы, у которых КЛЮЧ state соответствует указанному значению.
В том же модуле была написана функция sort_by_date. Она принимает список словарей и необязательный параметр, задающий порядок сортировки (по умолчанию - убывание). Функция возвращает новый список, отсортированный по дате ( date ).
Был создан README - файл для проекта. В нём описаны цель проекта, инструкции по установке и использованию разработанных функций, а также приведены примеры работы с ними.

---

|10.2|

Библиотека pytest была использована для написания тестов для существующего кода проекта. Тесты были созданы для всех основных функций, включая функции маскировки номеров карт и счетов, а также функции обработки дат и фильтрации данных.
Фикстуры были применены для создания необходимых входных данных для тестов. С помощью фикстур были подготовлены тестовые данные, такие как примеры номеров карт, счетов и списков словарей для проверки функций фильтрации и сортировки.
Параметризация была использована в тестах для обеспечения тестирования функциональности с различными входными данными. -Тесты были параметризованы для проверки функций на различных наборах данных, что позволило избежать дублирования кода и обеспечить тестирование.
Покрытие тестами было доведено до 80% и выше. С помощью инструмента pytest-cov было измерено покрытие кода тестами. Все ключевые функции и модули были протестированы, а покрытие составило более 80%, что подтверждается отчётом.

---

|11.1|

Работа с GitHub выполнена: домашнее задание сдано через pull request из ветки домашней работы в ветку develop, в коммиты не добавлены игнорируемые файлы, а README дополнен информацией о новом модуле и примерах использования реализованных функций.
В части создания генераторов был создан модуль generators. Реализована функция filter_by_currency, которая принимает список словарей на вход и возвращает итератор. Также реализована функция-генератор transaction_descriptions, принимающая на вход список словарей и использующая yield для генерации значений по запросу. Кроме того, реализован генератор card_number_generator, который принимает значения start и stop в качестве аргумента.
В области тестирования написаны тесты для функции filter_by_currency, функции transaction_descriptions и функции-генератора card_number_generator. Функциональный код покрыт тестами более чем на 80%, и при запуске тестов командой pytest все тесты завершаются успешно. В тестах используются фикстуры для генерации данных и параметризация для проверки различных кейсов работы функций. В репозитории также есть папка с отчетом покрытия тестами в формате HTML.
Оформление кода соответствует требованиям: при запуске линтера Flake8 выдается не более 5 ошибок, для всех реализованных функций написаны docstring, а нейминг функций отвечает правилам оформления кода PEP 8.
В работе с линтерами и форматерами при вызове isort форматируется не более 1 импорта.