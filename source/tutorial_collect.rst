Туториал: Сбор данных на местности
===================================

.. admonition:: Доступно

    облако, на своём сервере (Extended, Enterprise)

NextGIS Web - платформа для хранения, управления и публикации геоданных. Она включает в себя подсистему для совместного сбора данных. В этом пошаговом руководстве вы научитесь создавать проекты сбора данных и опробуете мобильное приложение для работы в поле. Создайте бесплатный аккаунт и попробуйте прямо сейчас!

В этом примере мы создадим проект для сбора данных о деревьях в городе. Для работы с мобильным приложением понадобится смартфон на базе Android.

Подготовка

* `Шаг 1. Создание бесплатного аккаунта и Веб ГИС <https://docs.nextgis.ru/docs_howto/source/tutorial_collect.html#account>`_
* `Шаг 2. Группа ресурсов <https://docs.nextgis.ru/docs_howto/source/tutorial_collect.html#webgis>`_
* `Шаг 3. Векторный слой (база данных) <https://docs.nextgis.ru/docs_howto/source/tutorial_collect.html#create-layer>`_
* `Шаг 4. Форма сбора данных <https://docs.nextgis.ru/docs_howto/source/tutorial_collect.html#form>`_ 
* `Шаг 5. Список участников <https://docs.nextgis.ru/docs_howto/source/tutorial_collect.html#collectors>`_
* `Шаг 6. Проект Collector <https://docs.nextgis.ru/docs_howto/source/tutorial_collect.html#project>`_

Сбор и просмотр данных

* `Ввод данных <https://docs.nextgis.ru/docs_howto/source/tutorial_collect.html#fieldwork>`_
* `Просмотр данных в Веб ГИС <https://docs.nextgis.ru/docs_howto/source/tutorial_collect.html#check>`_





.. _account:

Шаг 1/6 Создание бесплатного аккаунта и Веб ГИС
------------------------------------------------

Зайдите на  `my.nextgis.com`, нажмите кнопку **Создать аккаунт** и зарегистрируйтесь на свой адрес электронной почты. 

После регистрации откроется страница аккаунта. Выберите в меню слева пункт **Веб ГИС**. Придумайте название (мы в этом примере будем использовать test-free.nextgis.com) и выберите ближайший Центр обработки данных (Москва в этом примере). Затем нажмите **Создать Веб ГИС**.

.. figure:: _static/tutorial_create_wg_ru.png
   :name: 
   :align: center
   :width: 20cm

Когда процесс создания завершится, вид страницы изменится. На ней появится прямая ссылка на вашу новую Веб ГИС.

.. figure:: _static/tutorial_my_wg_ru.png
   :name: 
   :align: center
   :width: 20cm

.. _webgis:

Шаг 2/6 Интерфейс Веб ГИС и создание группы ресурсов
-------------------------------------------------------

Нажмите на адрес Веб ГИС или скопируйте его в строку браузера.

Отроется основной интерфейс вашей Веб ГИС.

.. figure:: _static/tutorial_wg_main_ru.png
   :name: tutorial_wg_main_pic
   :align: center
   :width: 20cm

NextGIS Web состоит из ресурсов. Слои, веб-карты, папки (группы), соединения с сервисами и подключения к базам данных - всё это ресурсы. Ресурсы организованы как файлы на компьютере - в виде "дерева". 

Создадим первый ресурс - папку или *группу ресурсов* - и назовём её "Сбор данных". Чтобы это сделать, нажмите синюю кнопку **Создать ресурс** в верхней части страницы. 

.. tip:: Если вы не видите кнопки **Создать ресурс**, вам нужно авторизоваться. Нажмите кнопку **Войти** в правом верхнем углу и выберите **Войти с помощью NextGIS ID**.

.. figure:: _static/tutorial_log_in_ru.png
   :name: tutorial_log_in_pic
   :align: center
   :width: 20cm

Кнопка **Создать ресурс** открывает окно с типами ресурсов, доступными для создания на той странице, где вы находитесь. Выберите **Группа ресурсов**.

.. figure:: _static/tutorial_select_group_ru.png
   :name: tutorial_select_group_pic
   :align: center
   :width: 20cm

Окно создания ресурса состоит из нескольких вкладок. Сейчас нам нужно только задать имя ``Сбор данных`` на вкладке "Ресурс".

.. figure:: _static/collect_create_group_ru.png
   :name: collect_create_group_pic
   :align: center
   :width: 16cm

Нажмите кнопку **Создать**. После успешного создания ресурса откроется его страница.

Адрес, отображающийся в строке браузера - это путь к ресурсу, а цифры на конце - идентификатор ресурса. 

.. figure:: _static/collect_group_result_ru.png
   :name: collect_group_result_pic
   :align: center
   :width: 16cm

Группа *Сбор данных* находится внутри *Основной группы ресурсов*, где мы её создали. Ресурс-родитель показан над наименованием ресурса.

Теперь можно загружать в эту папку данные.

.. _create_layer:

Шаг 3/6 Создание векторного слоя (в него будут собираться данные)
------------------------------------------------------------------

Теперь нужно создать векторный слой - базу данных, в которую будет собираться информация о географических объектах. Нажмите кнопку **Создать ресурс** и выберите **Векторный слой**.

.. figure:: _static/collect_select_layer_ru.png
   :name: collect_select_layer_pic
   :align: center
   :width: 20cm

Можно загрузить векторный слой из файла или создать с нуля. Откройте выпадающее меню и выберите **Создать пустой слой**.

.. figure:: _static/collect_create_empty_layer_ru.png
   :name: collect_create_empty_layer_pic
   :align: center
   :width: 16cm

Интерфейс вкладки изменится. Выберите в качестве типа геометрии **Точка**.

.. figure:: _static/collect_empty_layer_geom_ru.png
   :name: tutorial_empty_layer_geom_pic
   :align: center
   :width: 16cm


На вкладке **Ресурс** задайте имя для нового слоя, например ``Деревья``, и нажмите кнопку **Создать**.

Когда слой будет создан, отроется его страница. На ней отображаются метаданные и структура слоя (пока она пустая).

.. figure:: _static/collect_vector_result_ru.png
   :name: collect_vector_result_pic
   :align: center
   :width: 20cm

.. _form:

Шаг 4/6 Создание формы сбора данных 
--------------------------------------

При создании формы мы решаем сразу две задачи:

1. Определяем, какие данные мы хотим собирать в векторный слой,
2. Создаём понятный интерфейс для сборщиков данных.

На странице ресурса векторного слоя нажмите **Создать ресурс** и выберите **Форма**.

.. figure:: _static/collect_select_form_ru.png
   :name: collect_select_form_pic
   :align: center
   :width: 20cm


Откроется диалог создания формы.

.. figure:: _static/collect_designer_interface_ru.png
   :name: collect_designer_interface_pic
   :align: center
   :width: 20cm

В этом конструкторе вы можете создать форму, которую сборщики увидят в приложении. 

Вкладка разбита по вертикали на три части:

* Слева: список доступных для добавления элементов; 
* Посередине: макет формы, которая будет отображаться на экране телефона; 
* Справа: настройки выбранного элемента.



Перетащите элемент **Надпись** в среднюю часть. Оно появится в макете, по умолчанию это надпись "Текст". 

.. figure:: _static/collect_add_label_ru.png
   :name: collect_add_label_pic
   :align: center
   :width: 20cm

Справа внизу в блоке **Свойства** отредактируйте текст надписи: ``Вид дерева``. Это будет названием для первого поля, которое мы добавим.

.. figure:: _static/collect_label_text_ru.png
   :name: collect_label_text_pic
   :align: center
   :width: 20cm

Теперь нужно добавить поле ввода данных. В первом поле сборщики будут выбирать из списка возможных видов деревьев. Выберите элемент **Выпадающий список** и перетащите его в макет. 

Появится диалог, в котором нужно выбрать, в какой атрибут слоя будут сохраняться данные, введённые в это поле.

.. figure:: _static/collect_dropdown_new_ru.png
   :name: collect_dropdown_new_pic
   :align: center
   :width: 20cm



Пока в нашем слое нет атрибутов, поэтому нужно нажать кнопку **Добавить**.  Задайте следующие параметры для нового поля:

* Ключ = ``species``,
* Название = ``Вид``,
* Тип данных = STRING (строка).

Нажмите синюю кнопку **Добавить**.

.. figure:: _static/collect_add_dropdown_ru.png
   :name: collect_add_dropdown_pic
   :align: center
   :width: 12cm

Затем нажмите **ОК** в диалоге "Привязка данных".

Теперь макет выглядит так:

.. figure:: _static/collect_dropdown_properties_ru.png
   :name: collect_dropdown_properties_pic
   :align: center
   :width: 20cm

Кликните по добавленному в макет элементу "Выпадающий список" и в панели Свойства активируйте флажки **Запоминать значение** и **Разрешить поиск**. 

Теперь нужно добавить список, из которого будут выбирать сборщики. Нажмите кнопку **Редактировать** рядом с пунктом "Опции". 

Появится пустая таблица. В колонку "Значение" впишите формулировку, которая будет записываться в базу данных, в колонку "Надпись" - то, что сборщик будет видеть в интерфейсе. 

В данном случае мы для простоты запишем в обе колонки одно и то же. 
Добавьте шесть вариантов: ``Тополь, Дуб, Ель, Сосна, Берёза, Другое``

.. figure:: _static/collect_dropdown_options_ru.png
   :name: collect_dropdown_options_pic
   :align: center
   :width: 14cm

Добавленные варианты сохраняются автоматически.

Теперь добавим простое поле, в котором можно поставить галочку. Перетащите в макет элемент **Флажок**. В окне "Привязка данных" добавьте новое поле со следующими параметрами:

* Ключ = ``damaged``, 
* Название = ``Повреждённое``, 
* Тип данных = INTEGER (целое число). 

В свойствах элемента настройте:

* Надпись = ``Дерево повреждено``. 

Вы получите следующий результат:

.. figure:: _static/collect_ckeckbox_ru.png
   :name: collect_ckeckbox_pic
   :align: center
   :width: 8cm

Следующий элемент, который мы добавим - **Дата и время**. В окне "Привязка данных" добавьте новое поле со следующими параметрами:

* Ключ = ``datetime``, 
* Название = ``Дата и время``, 
* Тип данных = DATETIME. 

В свойствах элемента установите *Тип* "Дата и время".

.. figure:: _static/collect_datetime_properties_ru.png
   :name: collect_datetime_properties_pic
   :align: center
   :width: 10cm


Теперь перетащите в макет элемент **Фото**. В свойствах элемента установите *Макс. число фото*: 5.

После добавления всех необходимых элементов формы нужно создать соответствующие поля в слое. Для этого активируйте пункт **Добавить недостающие поля в слой**. В итоге форма должна выглядеть так:

.. figure:: _static/collect_add_absent_ru.png
   :name: collect_add_absent_pic
   :align: center
   :width: 20cm


Нажмите кнопку **Создать**. После создания формы вы будете перенаправлены на её страницу ресурса. 

Чтобы эту форму для сбора данных могли использовать сборщики, их нужно добавить в список участников сбора данных.

.. _collectors:

Шаг 5/6 Создайте список участников сбора данных
---------------------------------------------------

Откройте меню в правом верхнем углу интерфейса NextGIS Web и выберите пункт **Панель управления**.

.. figure:: _static/collect_open_control_panel_ru.png
   :name: collect_open_control_panel_pic
   :align: center
   :width: 8cm


Перейдите в раздел **Проекты Collector**.

.. figure:: _static/collect_control_panel_collector_ru.png
   :name: collect_control_panel_collector_pic
   :align: center
   :width: 8cm

Здесь можно редактировать список пользователей, добавленных в вашу Веб ГИС в качестве сборщиков данных. Любой пользователь, имеющий аккаунт NextGIS ID, может быть добавлен как сборщик данных, даже если он не входит в вашу `команду <https://docs.nextgis.com/docs_ngcom/source/teams.html>`_.

Изначально этот список пустой.

.. figure:: _static/collect_list_empty_ru.png
   :name: collect_list_empty_pic
   :align: center
   :width: 20cm


Чтобы добавить пользователя в список сборщиков, нажмите **Добавить**. Для начала добавьте себя. В поле NextGIS ID введите адрес электронной почты, который вы использовали при регистрации на my.nextgis.com.

.. figure:: _static/collect_add_collector_ru.png
   :name: collect_add_collector_pic
   :align: center
   :width: 20cm

В список будет добавлена новая запись.

.. _project:

Шаг 6/6 Создание проекта Collector
----------------------------------

Вернитесь в группу *Сбор данных* и создайте новый ресурс **Проект Collector**.

.. figure:: _static/collector_select_project_ru.png
   :name: collector_select_project_pic
   :align: center
   :width: 20cm

На вкладке "Ресурс" задайте имя проекта, которое сборщики будут видеть в приложении. Введите ``Деревья в городе``.

.. figure:: _static/collect_project_name_ru.png
   :name: collect_project_name_pic
   :align: center
   :width: 16cm

На вкладке "Проект" введите логин и пароль администратора Веб ГИС (электронную почту и пароль вашего NextGID ID).

.. figure:: _static/collect_project_settings_ru.png
   :name: collect_project_settings_pic
   :align: center
   :width: 16cm

На вкладке "Элементы" настраивается содержимое проекта. Какие данные должны быть видны сотрудникам, работающим в поле? Какие слои должны отображаться на карте, чтобы они могли сориентироваться? Нажмите **+ Слой** и выберите слой ``Деревья``.

.. figure:: _static/collect_project_items_ru.png
   :name: collect_project_items_pic
   :align: center
   :width: 20cm

Кликните по добавленному элементу, чтобы увидеть его свойства в панели справа. 
Проверьте, чтобы были активированы пункты *Редактируемый* и *Синхронизируемый*.

.. figure:: _static/collect_item_properties_ru.png
   :name: collect_item_properties_pic
   :align: center
   :width: 20cm

На вкладке "Участники" поставьте флажок напротив своего адреса электронной почты - это добавит вас в качестве сборщика в этот проект.

.. figure:: _static/collect_tick_collectors_ru.png
   :name: collect_tick_collectors_pic
   :align: center
   :width: 20cm


На этом всё. Нажмите **Создать**.

Проект создан, теперь можно начинать работу в поле.

В этом проекте в роли сборщика выступите вы сами.

.. _fieldwork:

Сбор данных в поле (работа сборщика)
-------------------------------------

Установите приложение NextGIS Collector на смартфон с ОС Android. Его можно найти в Google Play.

Запустите приложение. Авторизуйтесь, используя адрес электронной почты и пароль своего NextGIS ID.

.. figure:: _static/collect_sign_in_ru.jpg
   :name: collect_sign_in_pic
   :align: center
   :width: 8cm

После входа вы увидите список доступных вам проектов. Выберите проект **Деревья в городе** и подтвердите, что хотите присоединиться к нему.

.. figure:: _static/collect_project_list_ru.png
   :name: collect_project_list_pic
   :align: center
   :width: 8cm

.. figure:: _static/collect_project_join_ru.png
   :name: collect_project_join_pic
   :align: center
   :width: 8cm

В проекте отображается список слоёв. В нашем проекте только один слой - *Деревья*. 

Подойдите к ближайшему дереву и нажмите **ПО GPS** - будут записаны текущие координаты вашего мобильного устройства и откроется форма ввода. 

.. figure:: _static/collect_using_gps_ru.png
   :name: collect_using_gps_pic
   :align: center
   :width: 8cm

Выберите вид дерева из списка, проверьте, повреждено ли оно, добавьте одну или несколько фотографий, затем нажмите |button_tick|, чтобы сохранить изменения.

.. |button_tick| image:: _static/button_tick.png
   :width: 6mm

.. figure:: _static/collect_tree_new_feature_ru.png
   :name: collect_tree_new_feature_pic
   :align: center
   :width: 8cm

.. figure:: _static/collect_add_photo_ru.png
   :name: collect_add_photo_pic
   :align: center
   :width: 8cm

Данные собраны. Можно перейти к следующему дереву и повторить процедуру.

.. _check:

Просмотр собранных данных в Веб ГИС
-----------------------------------

Вернитесь в Веб ГИС и откройте векторный слой *Деревья*. В метаданных отображается количество объектов в слое. Эта информация синхронизируется, когда собранные данные загружаются в облако.

.. figure:: _static/collect_feature_count_ru.png
   :name: collect_feature_count_pic
   :align: center
   :width: 18cm



Чтобы посмотреть объект, нажмите на кнопку предпросмотра:

.. figure:: _static/collect_preview_layer_ru.png
   :name: collect_preview_layer_pic
   :align: center
   :width: 18cm

Также вы можете посмотреть значения атрибутов в таблице объектов:

.. figure:: _static/collect_feature_table_ru.png
   :name: collect_feature_table_pic
   :align: center
   :width: 18cm

Откройте предпросмотр объекта, чтобы увидеть прикреплённые фотографии.

.. figure:: _static/collect_feature_preview_ru.png
   :name: collect_feature_preview_pic
   :align: center
   :width: 22cm

Это позволяет в реальном времени отслеживать процесс сбора данных. Слой, в который записываются данные, можно использовать как любой другой - добавлять на веб-карту, публиковать в форме тайлов или по протоколам OGC, скачивать, добавлять в QGIS и т.п.
