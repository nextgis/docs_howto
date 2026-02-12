Туториал: Бесшовная интеграция с QGIS
=====================================

.. |ngconnect_icon| image:: _static/ngconnect_logo-45.png
   :width: 6mm
   :alt: голубой щит с белыми стрелками

.. |button_settings| image:: _static/button_settings.png
   :width: 6mm
   :alt: шестерёнка

.. |symbologyAdd| image:: _static/symbologyAdd.png
   :width: 6mm
   :alt: зелёный +

.. |button_to_wg| image:: _static/button_to_wg.png
   :width: 6mm

.. |button_to_qgis| image:: _static/button_to_qgis.png
   :width: 6mm

.. |NextGISLogo| image:: _static/NextGISLogo.png
   :width: 6mm
   :alt: сине-чёрный X

.. |synchronized| image:: _static/synchronized.png
   :width: 6mm

.. |mActionToggleEditing| image:: _static/mActionToggleEditing.png
   :width: 6mm

.. |mActionSaveEdits| image:: _static/mActionSaveEdits.png
   :width: 6mm
   
.. |button_add_point| image:: _static/button_add_point.png
   :width: 6mm


.. admonition:: Доступно

   Облако (все редакции), на своём сервере (все редакции), Open Source

NextGIS Web - платформа для хранения, управления и публикации геоданных. Она тесно связана с QGIS, ведущим бесплатным ПО в сфере ГИС с открытым кодом. 

Благодаря этой интеграции вы можете опубликовать проекты QGIS как веб-карты, подключаться к веб-картам как если бы это были проекты QGIS, синхронизировать данные и совместно редактировать их одновременно с нескольких устройств.

В этом пошаговом руководстве вы узнаете, как опубликовать проект QGIS в интернете, установить соединение с ним с другого компьютера, управлять стилями на веб-карте из QGIS и редактировать данные на сервере напрямую из настолького приложения QGIS. Создайте бесплатный аккаунт и попробуйте прямо сейчас!

:download:`Скачайте образец данных <https://nextgis.com/tutorials/seamless_qgis_integration_ru.zip>` (источники: `OpenStreetMap <https://www.openstreetmap.org/>`_, `data.nextgis.com <http://data.nextgis.com>`_, `Copernicus <https://browser.dataspace.copernicus.eu/>`_)

.. seealso:: `Пространственные данные - хранение, управление, публикация <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html>`_

Как опубликовать свой проект QGIS в интернете.

1. `Создание бесплатного аккаунта и Веб ГИС <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#account>`_
2. `Открытие проекта в QGIS <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#project>`_
3. `Установка модуля NextGIS Connect <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#install>`_
4. `Создание соединения <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#connection>`_
5. `Публикация проекта QGIS в Веб ГИС <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#publish>`_

Результат: `Просмотр веб-карты и ресурсов <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#webmap>`_

Как редактировать данные облачного хранилища в QGIS 

6. `Подключение к веб-карте из QGIS <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#download>`_
7. `Редактирование слоёв на веб-карте с помощью QGIS <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#vector_style>`_ 
8. `Обновление растрового стиля на веб-карте <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#raster_style>`_
9. `Редактирование данных в QGIS и их просмотр на веб-карте <https://docs.nextgis.ru/docs_howto/source/tutorial_qgis.html#edit_data>`_

.. _account:

Шаг 1/5 Создание бесплатного аккаунта и Веб ГИС
-----------------------------------------------

Зайдите на  `my.nextgis.com`, нажмите кнопку **Создать аккаунт** и зарегистрируйтесь на свой адрес электронной почты. 

После регистрации откроется страница аккаунта. Выберите в меню слева пункт **Веб ГИС**. Придумайте название (мы в этом примере будем использовать test-free.nextgis.com) и выберите ближайший Центр обработки данных (Москва в этом примере). Затем нажмите **Создать Веб ГИС**.

.. figure:: _static/tutorial_create_wg_ru.png
   :name: tutorial_create_wg_pic
   :align: center
   :width: 20cm

Когда процесс создания завершится, вид страницы изменится. На ней появится прямая ссылка на вашу новую Веб ГИС.

.. figure:: _static/tutorial_my_wg_ru.png
   :name: tutorial_my_wg_pic
   :align: center
   :width: 20cm

Скопируйте адрес созданной Веб ГИС. В нашем примере это ``https://ngw-quickstart.nextgis.com``. Он понадобится для создания подключения.

.. _project:

Шаг 2/5 Открытие проекта в QGIS
---------------------------------

`Скачайте пример данных <https://nextgis.com/tutorials/seamless_qgis_integration_ru.zip>`_ и распакуйте архив.

Кликните дважды на файле ``Suzdal.qgz``, чтобы открыть его в QGIS. 

.. note:: Если у вас ещё нет программы QGIS, вы можете `скачать <https://my.nextgis.com/software>`_ и установить её.

Это типичный проект QGIS, в котором есть растровые и векторные слои, пара базовых карт и разнообразные стили, зависящие от масштаба. Для отображения точек общественного питания используется динамическая кластеризация. Для слоя "Туризм" используются встроенные SVG-значки.

.. figure:: _static/tut_suzdal_project_ru.png
   :name: tut_suzdal_project_pic
   :align: center
   :width: 22cm


Меняйте масштаб колёсиком мыши или кнопками панели инструментов, чтобы увидеть, как меняются стили в зависимости от приближения.

.. figure:: _static/tut_project_zoomed_ru.png
   :name: tut_project_zoomed_pic
   :align: center
   :width: 22cm

.. _install:

Шаг 3/5 Установка модуля NextGIS Connect
----------------------------------------

В меню "Модули" выберите "Управление модулями".

.. figure:: _static/tut_menu_manage_plugins_ru.png
   :name: tut_menu_manage_plugins_pic
   :align: center
   :width: 16cm


Перейдите на вкладку "Все" и найдите модуль NextGIS Connect. Впишите название в строку поиска, чтобы быстро найти его. Нажмите **Установить модуль**.

Если вы используете NextGIS QGIS, этот модуль входит в сборку и уже установлен. Вместо кнопки "Установить" вы увидите надпись **Обновить модуль**. Обновите его до актуальной версии.

.. figure:: _static/tut_install_ngconnect_ru.png
   :name: tut_install_ngconnect_pic
   :align: center
   :width: 18cm

   Установка модуля

.. figure:: _static/tut_update_ngconnect_ru.png
   :name: tut_update_ngconnect_pic
   :align: center
   :width: 18cm

   Обновление модуля

После установки модуль NextGIS Connect доступен в меню "Интернет" и в панели инструментов: |ngconnect_icon|. Когда модуль активен, в интерфейсе отображается его панель.

.. figure:: _static/tut_ngconnect_in_qgis_ru.png
   :name: tut_ngconnect_in_qgis_pic
   :align: center
   :width: 22cm

Перейдите в настройки модуля, нажав кнопку |button_settings|. Здесь вы найдёте все настройки, связанные с интеграцией QGIS с NextGIS Web. Для начала установим соединение с Веб ГИС. 

.. _connection:

Шаг 4/5 Создание соединения
-----------------------------

Чтобы установить связь между QGIS и Веб ГИС, нужно создать соединение. 

В личном кабинете NextGIS ID перейдите на `страницу Веб ГИС <https://my.nextgis.com/webgis/>`_ и скопируйте ссылку на свою Веб ГИС (см. :numref:`tutorial_my_wg_pic`). В нашем примере ссылка выглядит так: ``https://ngw-quickstart.nextgis.com``.


В QGIS откройте настройки NG Connect и в разделе "Соединения" нажмите **Новое**.

.. figure:: _static/tut_ngcn_new_connection_ru.png
   :name: tut_ngcn_new_connection_pic
   :align: center
   :width: 20cm


В поле URL вставьте скопированный адрес Веб ГИС, затем нажмите |symbologyAdd|, чтобы создать новую конфигурацию аутентификации.

.. figure:: _static/tut_ngcn_create_connection_ru.png
   :name: tut_ngcn_create_connection_pic
   :align: center
   :width: 11cm

В следующем диалоговом окне введите адрес электронной почты и пароль, которые вы использовали при регистрации на my.nextgis.com на шаге 1, затем нажмите **Сохранить**.

.. figure:: _static/tut_ngcn_authentication_ru.png
   :name: tut_ngcn_authentication_pic
   :align: center
   :width: 10cm

Нажмите **Проверка подключения**, чтобы убедиться, что все данные введены правильно. Нажмите кнопку **Сохранить**.

.. figure:: _static/tut_ngcn_test_connection_ru.png
   :name: tut_ngcn_test_connection_pic
   :align: center
   :width: 11cm

.. tip:: Чтобы **редактировать данные совместно** с коллегами, включите галочку “Включить версионирование объектов для загружаемых векторных слоёв”.

.. figure:: _static/tut_enable_versioning_ru.png
   :name: tut_enable_versioning_pic
   :align: center
   :width: 20cm

Нажмите **ОК** внизу окна, чтобы применить изменения и закрыть настройки. 

Теперь в панели NextGIS Connect отобразится дерево ресурсов вашей Веб ГИС.

.. figure:: _static/tut_ngcn_panel_connected_ru.png
   :name: tut_ngcn_panel_connected_pic
   :align: center
   :width: 9cm

С помощью этой панели вы можете загружать локальные данные в Веб ГИС, управлять откреплёнными слоями и картами в QGIS, обновлять стили, создавать сервисы и многое другое. Также есть простой способ загрузить проект QGIS целиком и создать из него веб-карту.

.. _publish:

Шаг 5/5 Публикация проекта QGIS в Веб ГИС
--------------------------------------------

В панели NextGIS Connect выберите папку *Основная группа ресурсов*, затем нажмите |button_to_wg| и выберите в выпадающем меню **Загрузить всё**.

.. figure:: _static/tut_upload_all_ru.png
   :name: tut_upload_all_pic
   :align: center
   :width: 9cm

Введите имя для своего проекта. В нашем примере это ``Суздаль``. В Веб ГИС будет создана группа ресурсов с таким названием, и в неё будут загружены все данные проекта.

.. figure:: _static/tut_upload_name_ru.png
   :name: tut_upload_name_pic
   :align: center
   :width: 8cm

Начинается загрузка. Статус процесса загрузки отображается в панели Connect.

.. figure:: _static/tut_upload_status_ru.png
   :name: tut_upload_status_pic
   :align: center
   :width: 9cm


Когда создание веб-карты успешно завершилось, она откроется в браузере. Также вы можете открыть её из панели Connect. Кликните правой кнопкой мыши по веб-карте в дереве ресурсов и в контекстном меню выберите "Открыть в браузере". 

Обратите внимание: все слои проекта также отображаются в панели NextGIS Connect.

.. figure:: _static/tut_open_in_browser_ru.png
   :name: tut_open_in_browser_pic
   :align: center
   :width: 9cm

Теперь вы можете изучить получившуюся веб-карту. Перейдите к следующему шагу, чтобы узнать, как подключить существующую веб-карту в QGIS.

.. _webmap:

Просмотр веб-карты и ресурсов
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Из проекта была создана веб-карта. Она выглядит точно так же, как исходный проект QGIS, потому что NextGIS Web использует стили QGIS для визуализации данных.

.. figure:: _static/tut_suzdal_webmap_ru.png
   :name: tut_suzdal_webmap_pic
   :align: center
   :width: 22cm

Вы можете включать и отключать отображение слоёв и отдельных категорий внутри слоёв. У веб-карты есть собственная ссылка, которой легко поделиться. Попробуйте инструменты, которые видите на веб-карте. Подробнее об их возможностях: https://docs.nextgis.ru/docs_ngweb/source/webmaps_client.html

Кликните по логотипу |NextGISLogo| в левом верхнем углу, чтобы перейти к основному интерфейсу со списком ресурсов.

.. figure:: _static/tut_goto_main_ru.png
   :name: tut_goto_main_pic
   :align: center
   :width: 10cm

Откройте папку "Суздаль". Для каждого слоя исходного проекта в ней был создан соответствующий ресурс.

Вы можете работать с загруженными векторными и растровыми данными независимо от веб-карты: изменять данные, публиковать их с использованием разных протоколов и т.д.

.. figure:: _static/tut_wg_suzdal_ru.png
   :name: tut_wg_suzdal_pic
   :align: center
   :width: 22cm

Загруженные слои также можно редактировать с помощью QGIS. Рассмотрим, как это сделать.

.. _download:

Подключение к веб-карте из QGIS
-----------------------------------

Закройте проект в QGIS (Проект - Закрыть). Представим себе, что вы работаете с другого компьютера, где также установлена программа QGIS. Оставьте открытой панель NextGIS Connect (или откройте её, если она не активна).

В панели NextGIS Connect найдите веб-карту "Суздаль - webmap", вызовите контекстное меню и выберите |button_to_qgis| **Добавить в QGIS**.

.. figure:: _static/tut_add_to_qgis_ru.png
   :name: tut_add_to_qgis_pic
   :align: center
   :width: 9cm

QGIS построит локальную копию содержимого веб-карты, скачав все нужные слои и стили и организовав их в проекте в аналогичную структуру.

По сути вы получаете исходный проект, восстановленный из облака.

.. figure:: _static/tut_downloaded_ru.png
   :name: tut_downloaded_pic
   :align: center
   :width: 22cm

Обратите внимание, что в панели Слои напротив слоёв появились специальные значки: |synchronized|.

.. figure:: _static/tut_synched_layers_ru.png
   :name: tut_synched_layers_pic
   :align: center
   :width: 14cm

Теперь они связаны с хранилищем на сервере. Если на стороне сервера произойдёт обновление данных, NG Connect синхронизирует локальный слой в QGIS. И наоборот, если слой будет обновлён в QGIS, Connect передаст эти изменения на сервер и обновит данные в Веб ГИС.

Это открывает много полезных возможностей, в первую очередь - обновление стилей на веб-карте.

.. _vector_style:

Редактирование слоёв на веб-карте с помощью QGIS
-------------------------------------------------

Сделаем дороги более заметными на веб-карте.

В QGIS , найдите слой *Дорожная сеть* в панели Слои. Вызовите контекстное меню категории "Улицы". В палитре выберите красный цвет. Нажмите на пустой части панели, чтобы закрыть диалоговое окно.

.. figure:: _static/tut_pick_color_ru.png
   :name: tut_pick_color_pic
   :align: center
   :width: 10cm

Теперь найдите и выберите слой *Дорожная сеть* в панели NextGIS Connect.

.. figure:: _static/tut_road_select_ru.png
   :name: tut_road_select_pic
   :align: center
   :width: 9cm

Перейдите в панель Слои, откройте контекстное меню слоя *Дорожная сеть* и выберите пункт **NextGIS Connect --> Обновить стиль слоя**.

.. figure:: _static/tut_update_v_style_ru.png
   :name: tut_update_v_style_pic
   :align: center
   :width: 16cm

Перейдите в браузер, где у вас открыта веб-карта (если вы закрыли окно, откройте его из панели NextGIS Connect через контекстное меню карты). Обновите страницу, и вы увидите, что улицы изменили цвет.

.. figure:: _static/tut_webmap_red_roads_ru.png
   :name: tut_webmap_red_roads_pic
   :align: center
   :width: 22cm


Стили растровых слоёв также можно изменять. 

.. _raster_style:

Обновление растрового стиля на веб-карте
-----------------------------------------

В QGIS активируйте слой *Sentinel 2*. Это данные спутниковой съёмки с 4 каналами. Сейчас они настроены на то, чтобы отображать естественные цвета видимого спектра.

.. figure:: _static/tut_raster_initial_ru.png
   :name: tut_raster_initial_pic
   :align: center
   :width: 22cm

Вызовите контекстное меню слоя и выберите "Свойства".

.. figure:: _static/tut_raster_context_ru.png
   :name: tut_raster_context_pic
   :align: center
   :width: 14cm

В диалоге свойств откройте вкладку "Стиль" и в пункте *Красный канал* выберите вместо ``Канал 1`` ``Канал 4`` Нажмите **ОК**.

.. figure:: _static/tut_raster_bands_ru.png
   :name: tut_raster_bands_pic
   :align: center
   :width: 22cm

Мы заменили стандартный красный канал на канал ближней инфракрасной области, и визуализация растра существенно изменилась.

.. figure:: _static/tut_raster_nir_ru.png
   :name: tut_raster_nir_pic
   :align: center
   :width: 22cm

Откройте веб-карту в браузере и активируйте слой Sentinel 2. Он выглядит так же, как и раньше.

.. figure:: _static/tut_raster_webmap_ru.png
   :name: tut_raster_webmap_pic
   :align: center
   :width: 22cm

Вернитесь в QGIS, выберите слой *Sentinel 2* в панели NextGIS Connect.

.. figure:: _static/tut_raster_select_ru.png
   :name: tut_raster_select_pic
   :align: center
   :width: 9cm

Теперь вызовите контекстное меню слоя в панели слоёв и нажмите **NextGIS Connect --> Обновить стиль слоя**.

.. figure:: _static/tut_update_r_style_ru.png
   :name: tut_update_r_style_pic
   :align: center
   :width: 18cm

Снова отройкте веб-карту в браузере — стиль слоя изменился. 

.. figure:: _static/tut_raster_webmap_nir_ru.png
   :name: tut_raster_webmap_nir_pic
   :align: center
   :width: 22cm

NextGIS Web может обрабатывать многоканальные растры со стилями QGIS любой сложности.

.. _edit_data:

Редактирование данных в QGIS и их просмотр на веб-карте
-------------------------------------------------------

Вернитесь в QGIS, в панели Слои выберите слой *Туризм* в группе *Точки интереса*, вызовите контекстное меню и включите |mActionToggleEditing| Режим редактирования. Поскольку слой был добавлен с помощью NextGIS Connect, он связан с Веб ГИС, и правки будут синхронизироваться с сервером.

.. figure:: _static/tut_toggle_editing_ru.png
   :name: tut_toggle_editing_pic
   :align: center
   :width: 12cm

Включите панель инструментов "Инструменты оцифровки" и активируйте инструмент |button_add_point| Добавить точечный объект

.. figure:: _static/tut_digitizing_ru.png
   :name: tut_digitizing_pic
   :align: center
   :width: 10cm

Добавим новую информационную табличку в парке. Кликните левой кнопкой мыши на подходящее место на карте, затем заполните одно поле: TOURISM=``information``. Нажмите **ОК**.

.. figure:: _static/tut_new_point_ru.png
   :name: tut_new_point_pic
   :align: center
   :width: 16cm

Нажмите |mActionToggleEditing|, чтобы выйти из режима редактирования и выберите **Сохранить**

.. figure:: _static/tut_qgis_stop_edit_ru.png
   :name: tut_qgis_stop_edit_pic
   :align: center
   :width: 22cm

После того, как вы выйдете из режима редактирования, синхронизация запустится автоматически. Созданный объект будет отправлен на сервер. Перейдите в браузер, чтобы увидеть его на веб-карте.

.. figure:: _static/tut_added_on_webmap_ru.png
   :name: tut_added_on_webmap_pic
   :align: center
   :width: 22cm

Несколько человек могут одновременно подключаться к одному серверу с разных устройств и редактировать данные одновременно. Наш стек предоставляет готовое решение для совместной оцифровки и редактирования данных в QGIS.





