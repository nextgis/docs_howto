Туториал: Пространственные данные - хранение, управление, публикация
=====================================================================

.. admonition:: Доступно

   Облако (все редакции), на своём сервере (все редакции), Open Source

NextGIS Web - платформа для хранения, управления и публикации геоданных. В этом пошаговом руководстве вы узнаете, как из ГИС-файлов получить интерактивную веб-карту, тайлы и сервисы OGC, а также как создавать данные и управлять ими напрямую на сервере. Создайте бесплатный аккаунт и попробуйте прямо сейчас!

:download:`Скачать пример данных <https://nextgis.com/tutorials/store_manage_publish_geospatial_data_ru.zip>` (источники: `Портал открытых данных Москвы <https://data.mos.ru/>`_, ESA)

Базовый уровень

1. `Создание бесплатного аккаунта и Веб ГИС <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#account>`_
2. `Создание группы ресурсов <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#webgis>`_
3. `Загрузка векторного слоя <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#vector>`_
4. `Загрузка стиля <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#style>`_
5. `Загрузка растрового слоя <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#raster>`_
6. `Публикация веб-карты <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#webmap>`_

Продвинутый уровень

7. `Добавление слоя WMS на веб-карту <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#wms-layer>`_
8. `Добавление подложки <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#basemap>`_
9. `Создание пустого векторного слоя в Веб ГИС <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#empty-layer>`_
10. `Редактирование слоя в Веб ГИС, вложения <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#edit>`_
11. `Публикация через OGC API Features <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#ogc-api>`_
12. `Следующие шаги <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#next>`_

.. _account:

Шаг 1/6 Создание бесплатного аккаунта и Веб ГИС
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

Создадим первый ресурс - папку или *группу ресурсов* - и назовём её "Москва". Чтобы это сделать, нажмите синюю кнопку **Создать ресурс** в верхней части страницы. 

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

Окно создания ресурса состоит из нескольких вкладок. Сейчас нам нужно только задать имя на вкладке "Ресурс".

.. figure:: _static/tutorial_create_group_ru.png
   :name: tutorial_create_group_pic
   :align: center
   :width: 20cm

Нажмите кнопку **Создать**. После успешного создания ресурса откроется его страница.

.. figure:: _static/tutorial_group_result_ru.png
   :name: tutorial_group_result_pic
   :align: center
   :width: 20cm

Адрес, отображающийся в строке браузера - это путь к ресурсу, а цифры на конце - идентификатор ресурса. 

Группа *Москва* находится внутри *Основной группы ресурсов*, где мы её создали. Ресурс-родитель показан над наименованием ресурса.

Теперь можно загружать в эту папку данные.

.. _vector:

Шаг 3/6 Загрузка и публикация векторного слоя
---------------------------------------------

`Скачайте пример данных <https://nextgis.com/tutorials/store_manage_publish_geospatial_data_ru.zip>`_ и распакуйте архив.

В группе ресурсов *Москва* нажмите **Создать ресурс** и выберите тип ресурса **Векторный слой**.

.. figure:: _static/tutorial_select_vlayer_ru.png
   :name: tutorial_select_vlayer_pic
   :align: center
   :width: 20cm

Отроется интерфейс создания ресурса с несколькими вкладками. 

.. figure:: _static/tutorial_create_vlayer_upload_ru.png
   :name: tutorial_create_vlayer_upload_pic
   :align: center
   :width: 16cm

По умолчанию открыта вкладка **Векторный слой**. Перетащите в поле загрузки файл ``bicycle_roads_moscow.geojson`` из папки с данными, или кликните по полю и выберите файл в открывшемся окне.

Когда файл загрузится, отобразится его размер. 

Переключитесь на вкладку **Ресурс** и введите наименование слоя, например, ``Велодорожки``. Затем нажмите кнопку **Создать**.

.. figure:: _static/tutorial_create_vlayer_name_ru.png
   :name: tutorial_create_vlayer_name_pic
   :align: center
   :width: 16cm

Когда слой будет создан, отроется его страница. Цифры в конце адреса этой страницы - ID слоя.

На этой странице отображается информация о слое:

* Место в дереве ресурсов (Основная группа ресурсов/Москва);
* Базовые метаданные (тип геометрии, количество объектов и т.п.);
* Список полей (структура атрибутов).

.. figure:: _static/tutorial_vlayer_result_ru.png
   :name: tutorial_vlayer_result_pic
   :align: center
   :width: 20cm

В разделе **Внешний доступ** находится автоматически сгенерированная ссылка, через которую данные доступны в виде тайлов MVT. Вы сразу можете подключить эти данные в веб-приложение или добавить их в QGIS по этой ссылке. `Подробнее о тайлах MVT <https://docs.nextgis.ru/docs_ngweb/source/services.html#ngw-mvt>`_.



Чтобы посмотреть данные, откройте Таблицу объектов, нажав кнопку |button_open_feature_table| **Таблица** в меню справа.

.. |button_open_feature_table| image:: _static/button_open_feature_table.png
   :width: 6mm


.. figure:: _static/tutorial_feature_table_ru.png 
   :name: tutorial_feature_table_pic
   :align: center
   :width: 24cm

Выберите любой объект и нажмите **Открыть**, чтобы посмотреть его.

В окне предпросмотра показаны свойства выбранного объекта, в том числе его атрибуты, данные о геометрии и визуализация поверх стандартной подложки.

.. figure:: _static/tutorial_feature_preview_ru.png 
   :name: tutorial_feature_preview_pic
   :align: center
   :width: 20cm

Через Таблицу объектов можно напрямую управлять векторными объектами. Вы можете просматривать и редактировать их как независимые записи базы данных, не используя карту или другие приложения. (`Подробнее <https://docs.nextgis.ru/docs_ngweb/source/feature_table.html#ngw-feature-table-blank>`_)

.. _style:

Шаг 4/6 Загрузка стиля
------------------------

Если вы хотите получить **тайлы TMS** или **добавить слой на веб-карту**, нужно определить, как он будет визуализироваться - то есть задать для него **стиль**. Можно нажать **Создать стиль QGIS по умолчанию**, но для этого слоя у нас есть файл, определяющий цвета и структуру линий в зависимости от их атрибутов.

На странице слоя нажмите кнопку **Создать ресурс**. Вы увидите другой набор доступных типов ресурсов, потому что дочерними ресурсами слоя могут быть только стили и формы. В качестве основного способа визуализации данных используются стили QGIS. Выберите **Векторный стиль QGIS**.

.. figure:: _static/tutorial_select_qstyle_ru.png
   :name: tutorial_select_qstyle_pic
   :align: center
   :width: 20cm

Загрузите файл ``bicycle_roads_moscow.qml`` из папки с примером. Затем нажмите кнопку **Создать**.

.. figure:: _static/tutorial_create_qstyle_ru.png
   :name: tutorial_create_qstyle_pic
   :align: center
   :width: 16cm

Будет создан стиль и откроется его страница. В меню справа нажмите **Просмотр**, чтобы увидеть, как выглядит стиль.

В разделе **Внешний доступ** вы найдёте автоматически сгенерированную ссылку, которую можно использовать, чтобы подключить стилизованные данные как тайлы Tiled Map Service, например, в QGIS. `Подробнее об использовании TMS <https://docs.nextgis.ru/docs_ngweb/source/services.html#ngw-tms-service>`_

Теперь можно добавить слой другого типа или сразу перейти к  `созданию веб-карты <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#step-6-6-publish-web-map>`_.

.. _raster:

Шаг 5/6 Загрузка и публикация растрового слоя
----------------------------------------------

Вернитесь в группу ресурсов *Москва*, нажав на её имя в пути к ресурсу.

.. figure:: _static/tutorial_return_folder_ru.png
   :name: tutorial_return_folder_pic
   :align: center
   :width: 20cm


Нажмите кнопку **Создать ресурс** и выберите **Растровый слой**.

.. figure:: _static/tutorial_select_raster_layer_ru.png
   :name: tutorial_select_raster_layer_pic
   :align: center
   :width: 20cm


На вкладке **Растровый слой** перетащите из папки с примером файл ``plan.tif`` или кликните по полю и выберите файл во всплывающем окне. Затем нажмите кнопку **Создать**.

.. figure:: _static/tutorial_raster_upload_ru.png
   :name: tutorial_raster_upload_pic
   :align: center
   :width: 16cm


Будет создан растровый слой и откроется его страница. На ней отображается:

* Место в дереве ресурсов (Основная группа ресурсов/Москва);
* Основные метаданные (каналы, размер и т.п.).



.. figure:: _static/tutorial_raster_result_ru.png
   :name: tutorial_raster_result_pic
   :align: center
   :width: 16cm

В разделе **Внешний доступ** вы найдёте автоматически сгенерированную ссылку для доступа к данным **Cloud Optimized GeoTIFF**. Эту ссылку можно сразу использовать для подключения данных во внешние ресурсы.

Визуализация растров происходит через создание дочерних ресурсов стилей. Для растров RGB(A) можно просто нажать **Создать стиль QGIS по умолчанию**. Давайте так и сделаем. Будет создан стандартный стиль и откроется его страница. 

.. figure:: _static/tutorial_def_raster_style_result_ru.png
   :name: tutorial_def_raster_style_result_pic
   :align: center
   :width: 16cm


Автоматически будет сгенерирована ссылка на сервис **растровых файлов (TMS)** на основе этих данных. Вы сразу можете использовать эту ссылку, чтобы подключить стилизованные растровые тайлы во внешние приложения.

Также можно нажать в панели справа **Просмотр**, чтобы посмотреть на растр с применённым стилем.

.. figure:: _static/tutorial_raster_preview_ru.png
   :name: tutorial_raster_preview_pic
   :align: center
   :width: 20cm

Теперь создадим веб-карту, на которой будут отображаться загруженные данные.

.. _webmap:

Шаг 6/6 Публикация веб-карты
----------------------------

Теперь, когда у нас есть несколько слоёв с добавленными к ним стилями, можно опубликовать первую веб-карту. Вернитесь в группу ресурсов *Москва* и выберите в меню создания ресурса тип **Веб-карта**.

.. figure:: _static/tutorial_select_webmap_ru.png
   :name: tutorial_select_webmap_pic
   :align: center
   :width: 20cm


У веб-карты много разных настроек. На вкладке "Ресурс" введите наименование карты, например, ``Москва``.

.. figure:: _static/tutorial_webmap_name_ru.png
   :name: tutorial_webmap_name_pic
   :align: center
   :width: 16cm


На вкладке **Слои** определяется содержимое карты. Нажмите кнопку |button_plus_layer| **Слой**. На карту добавляется визуальное представление данных, поэтому выбрать нужно стиль, а не слой. Флажок выбора при имени слоя будет не активен. Вы можете зайти внутрь слоя и выбрать дочерний ресурс стиля или просто нажать на иконку |button_pick_first| **Выбрать первый подходящий дочерний ресурс** справа от слоя. Отметьте стили в слоях *Велодорожки* и *plan*.

.. |button_pick_first| image:: _static/button_pick_first.png
   :width: 6mm

.. |button_plus_layer| image:: _static/button_plus_layer.png
   :width: 6mm


.. figure:: _static/tutorial_webmap_add_layers_ru.png
   :name: tutorial_webmap_add_layers_pic
   :align: center
   :width: 20cm


Нажмите на слой, чтобы настроить его свойства.

.. figure:: _static/tutorial_webmap_layer_settings_ru.png
   :name: tutorial_webmap_layer_settings_pic
   :align: center
   :width: 16cm


Перейдите на вкладку **Настройки**. В строке "Начальный охват" нажмите кнопку **Вычислить охват из всех слоёв**.  Теперь карта будет открываться на области, охватывающей все добавленные на неё данные.

.. figure:: _static/tutorial_webmap_extent_ru.png
   :name: tutorial_webmap_extent_pic
   :align: center
   :width: 20cm


Нажмите **Создать**, чтобы завершить создание веб-карты. 

Для ресурса веб-карты существует особый режим просмотра. Нажмите **Открыть** в меню справа.

.. figure:: _static/tutorial_webmap_display_ru.png
   :name: tutorial_webmap_display_pic
   :align: center
   :width: 20cm


Или, если вы вернулись в группу ресурсов *Москва*, нажмите на значок с картой и лупой |button_open_web_map| справа от наименования ресурса веб-карты.

.. |button_open_web_map| image:: _static/button_open_web_map.png
   :width: 6mm

Откроется инерактивная веб-карта. У каждой карты есть собственная ссылка на просмотр и множество инструментов для управления данными. 

.. figure:: _static/tutorial_webmap_displayed_ru.png
   :name: tutorial_webmap_displayed_pic
   :align: center
   :width: 20cm

Панели, расположенные с левой стороны, позволяют управлять слоями карты, идентифицировать и редактировать объекты, а также поделиться картой и вывести её на печать. Подробную информацию об инструментах веб-карты и панелях вы найдёте в документации: https://docs.nextgis.ru/docs_ngweb/source/webmaps_client.html

Вы можете создавать сколько угодно веб-карт с разными сочетаниями доступных слоёв и их стилей.

Дальше вы можете:

* `Добавить на веб-карту слой из внешнего источника <https://docs.nextgis.com/docs_howto/source/tutorial_webgis.html#>`_;
* `Добавить свою подложку <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#basemap>`_;
* `Создать пустой векторный слой <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#empty-layer>`_;
* `Редактировать векторные объекты и добавлять вложения <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#edit>`_;
* `Опубликовать данные через сервис OGC API Features <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#ogc-api>`_.

.. _wms_layer:

Добавление внешнего слоя WMS на веб-карту
-----------------------------------------

В NextGIS Web можно подключать внешние данные через протоколы :term:`WMS`, :term:`WFS`, :term:`TMS` и :term:`PostGIS`. Например, добавим спутниковый снимок из публичного сервиса WMS.

Вернитесь в группу *Москва* и создайте новый ресурс: **Соединение WMS**.

.. figure:: _static/tutorial_select_wms_con_ru.png
   :name: tutorial_select_wms_con_pic
   :align: center
   :width: 20cm


На вкладке "Ресурс" введите наименование: ``Спутниковый снимок - сервис``.

.. figure:: _static/tutorial_wms_con_name_ru.png
   :name: tutorial_wms_con_name_pic
   :align: center
   :width: 16cm


На вкладке "WMS соединение" введите адрес: https://demo.nextgis.ru/api/resource/10551/wms?service=WMS&request=GetCapabilities

.. figure:: _static/tutorial_wms_con_link_ru.png
   :name: tutorial_wms_con_link_pic
   :align: center
   :width: 16cm


Затем нажмите кнопку **Создать**.

Вернитесь в группу *Москва* и создайте ресурс другого типа - **Слой WMS**.

.. figure:: _static/tutorial_select_wms_layer_ru.png
   :name: tutorial_select_wms_layer_pic
   :align: center
   :width: 20cm


На вкладке "Ресурс" задайте имя - ``Спутниковый снимок - слой``

.. figure:: _static/tutorial_wms_layer_name_ru.png
   :name: tutorial_wms_layer_name_pic
   :align: center
   :width: 16cm


На вкладке **Слой WMS** нажмите на поле **WMS соединение** и выберите ресурс **Спутниковый снимок - сервис**, затем нажмите **Выбрать отмеченное**.

.. figure:: _static/tutorial_wms_layer_pick_con_ru.png
   :name: tutorial_wms_layer_pick_con_pic
   :align: center
   :width: 20cm


В выпадающем меню *Формат изображения* выберите **image/png**. В выпадающем меню *Слои WMS* выберите **Moscow Sentinel-2**.

.. figure:: _static/tutorial_wms_layer_settings_ru.png
   :name: tutorial_wms_layer_settings_pic
   :align: center
   :width: 16cm


Затем нажмите кнопку **Создать**. Итак, соединение и слой WMS созданы. 

В разделе **Внешний доступ** вы найдёте автоматически сгенерированную ссылку, которую можно использовать для подключения данных в виде **растровых тайлов**. Вы сразу можете добавить эти данные в веб-приложение или настольную программу, например, NextGIS QGIS. Ваша Веб ГИС будет выступать в качестве прокси для WMS-сервиса.

.. figure:: _static/tutorial_wms_layer_result_ru.png
   :name: tutorial_wms_layer_result_pic
   :align: center
   :width: 20cm


Чтобы **добавить слой WMS на веб-карту** вернитесь в группу *Москва* и нажмите иконку с карандашом |button_edit| рядом с веб-картой.

.. |button_edit| image:: _static/button_edit.png
   :width: 6mm
   :alt: карандаш

.. figure:: _static/tutorial_webmap_edit_select_ru.png
   :name: tutorial_webmap_edit_select_pic
   :align: center
   :width: 20cm


На вкладке **Слои** нажмите кнопку |button_plus_layer| **Слой**, выберите **Спутниковый снимок - слой** и нажмите кнопку **Выбрать отмеченное**. Слой WMS добавлен на веб-карту.

.. figure:: _static/tutorial_webmap_add_wms_ru.png
   :name: tutorial_webmap_add_wms_pic
   :align: center
   :width: 20cm


Сохраните ресурс и отройте карту в режиме просмотра. Вы увидите, что спутниковый снимок из внешнего источника теперь отображается под ранее загруженными данными.

.. figure:: _static/tutorial_webmap_with_wms_ru.png
   :name: tutorial_webmap_with_wms_pic
   :align: center
   :width: 20cm


.. _basemap:

Добавление подложки на веб-карту
--------------------------------

По умолчанию в веб-картах используется стандартная подложка OpenStreetMap. Но вы можете добавить другие подложки и использовать их в своих веб-картах.

Вернитесь в группу *Москва* и выберите тип создаваемого ресурса **Подложка веб-карты**.

.. figure:: _static/tutorial_select_basemap_ru.png
   :name: tutorial_select_basemap_pic
   :align: center
   :width: 20cm


Здесь вы можете воспользоваться нашим открытым каталогом источников геоданных qms.nextgis.com. Начните вводить название подложки в поле **Выбрать из QMS** и выберите нужную из списка найденных в каталоге.

.. figure:: _static/tutorial_qms_pick_poistron_ru.png
   :name: tutorial_qms_pick_poistron_pic
   :align: center
   :width: 16cm

Остальные поля будут заполнены автоматически. Внизу отобразится превью подложки.

Также подложку можно создать, вручную введя ссылку на тайлы в поле URL. 

Переключатель в правом углу окна предпросмотра позволяет сравнить создаваемую подложку со стандартной базовой картой OpenStreetMap.

.. figure:: _static/tutorial_basemap_preview_ru.png
   :name: tutorial_basemap_preview_pic
   :align: center
   :width: 16cm



На вкладке **Ресурс** задайте имя для подложки.


.. figure:: _static/tutorial_basemap_name_ru.png
   :name: tutorial_basemap_name_pic
   :align: center
   :width: 16cm

Нажмите кнопку **Создать**.

Чтобы добавить только что созданную подложку на веб-карту, вернитесь в группу *Москва* и нажмите иконку "Изменить" |button_edit| рядом с веб-картой.

.. figure:: _static/tutorial_webmap_edit_select_ru.png
   :name: tutorial_webmap_enter_update_pic2
   :align: center
   :width: 20cm

На вкладке **Подложки** нажмите кнопку  |button_plus_layer| **Добавить** и выберите созданный ресурс подложки. Затем нажмите **Выбрать отмеченное** и сохраните изменения.

.. figure:: _static/tutorial_webmap_add_basemap_ru.png
   :name: tutorial_webmap_add_basemap_pic
   :align: center
   :width: 20cm

Откройте просмотр |button_open_web_map| веб-карты. Теперь на карте отображается новая подложка.

.. figure:: _static/tutorial_webmap_positron_ru.png
   :name: tutorial_webmap_positron_pic
   :align: center
   :width: 20cm

.. _empty_layer:

Создание пустого векторного слоя в Веб ГИС
-------------------------------------------

Можно не только загружать данные из файлов, но и создавать наборы данных напрямую в Веб ГИС. 

Вернитесь в группу *Москва* и создайте новый ресурс **Векторный слой**.

.. figure:: _static/tutorial_select_vlayer_ru.png
   :name: tutorial_select_empty_layer_pic
   :align: center
   :width: 20cm

На вкладке "Векторный слой" откройте выпадающее меню и выберите **Создать пустой слой**.

.. figure:: _static/tutorial_create_empty_layer_ru.png
   :name: tutorial_create_empty_layer_pic
   :align: center
   :width: 16cm

Интерфейс вкладки изменится. Выберите в качестве типа геометрии **Точка**.

.. figure:: _static/tutorial_empty_layer_geom_ru.png
   :name: tutorial_empty_layer_geom_pic
   :align: center
   :width: 16cm


На вкладке **Ресурс** задайте имя для нового слоя, например ``Велопарковки``, и нажмите кнопку **Создать**.

.. figure:: _static/tutorial_empty_layer_name_ru.png
   :name: tutorial_empty_layer_name_pic
   :align: center
   :width: 16cm

Когда слой будет создан, отроется его страница. Теперь нужно добавить атрибуты. Нажмите |button_edit| **Изменить** в меню справа.

.. figure:: _static/tutorial_empty_layer_result_ru.png
   :name: tutorial_empty_layer_result_pic
   :align: center
   :width: 20cm


Перейдите на вкладку **Поля** и нажмите кнопку |button_plus_layer| **Добавить**.

Кликните на созданное поле и настройте его свойства в панели справа: 

* Наименование: ``Количество парковочных мест``, 
* Ключ: ``parking_spaces``, 
* Тип: INTEGER. 



.. figure:: _static/tutorial_add_field_ru.png
   :name: tutorial_add_field_pic
   :align: center
   :width: 16cm

Нажмите кнопку **Сохранить**.

Теперь нужно добавить к новому слою стиль. На странице ресурса векторного слоя нажмите **Создать ресурс** и выберите **Векторный стиль QGIS**. 

На вкладке **Стиль QGIS** откройте выпадающее меню и выберите **Пользовательский стиль**.

.. figure:: _static/tutorial_style_custom_select_ru.png
   :name: tutorial_style_custom_select_pic
   :align: center
   :width: 16cm

Здесь доступен конструктор простых стилей. Мы рекомендуем создавать стили в QGIS, но для быстрого добавления встроенный конструктор может быть полезен. Настойте в конструкторе значок в виде синего кружка с белой обводкой, размер - 12, толщина обводки - 1. Затем нажмите кнопку **Создать**.

.. figure:: _static/tutorial_style_custom_set_ru.png
   :name: tutorial_style_custom_set_pic
   :align: center
   :width: 16cm


В Веб ГИС создан новый векторный слой. 

Теперь его можно добавить на веб-карту и `опубликовать через сервис OGC <https://docs.nextgis.ru/docs_howto/source/tutorial_webgis.html#publish-ogc-api-features-service>`_.

Но сначала добавим на новый слой несколько объектов, используя веб-интерфейс.

.. _edit:

Редактирование векторного слоя на веб-карте, добавление вложений
----------------------------------------------------------------

Вернитесь в группу *Вроцлав* и зайдите в режим |button_edit| изменения ресурса веб-карты.

.. figure:: _static/tutorial_webmap_edit_select_ru.png
   :name: tutorial_webmap_edit_select_pic3
   :align: center
   :width: 20cm


Сначала откройте владку **Слои**, нажмите |button_plus_layer| **Слой** и добавьте *Велопарковки*, кликнув по иконке |button_pick_first| **Первый подходящий дочерний ресурс** справа от имени слоя. Нажмите **Выбрать отмеченные**, затем перетащите слой *Велопарковки* на самый верх списка слоёв.

.. figure:: _static/tutorial_webmap_add_empty_ru.png
   :name: tutorial_webmap_add_empty_pic
   :align: center
   :width: 20cm

Далее перейдите на вкладку **Настройки**, найдите выпадающее меню **Редактирование слоёв** и выберите **Включить**. Сохраните изменения.

.. figure:: _static/tutorial_webmap_enable_editing_ru.png
   :name: tutorial_webmap_enable_editing_pic
   :align: center
   :width: 16cm

Теперь на карту добавлен новый векторный слой и включена возможность редактирования слоёв. Откройте  |button_open_web_map| веб-карту в режиме просмотра.

.. figure:: _static/tutorial_webmap_display_ru.png
   :name: tutorial_webmap_display_pic2
   :align: center
   :width: 20cm

Приблизьтесь к месту на карте, где хотите отметить новую парковку. Откройте контекстное меню слоя, нажав на три точки справа от его имени, и выберите |button_edit| **Редактировать**.

.. figure:: _static/tutorial_layer_start_edit_ru.png
   :name: tutorial_layer_start_edit_pic
   :align: center
   :width: 10cm

На карте появятся новые инструменты. 

Выберите инструмент добавления |button_maptool_plus| и кликните по нужному месте на карте.

.. |button_maptool_plus| image:: _static/button_maptool_plus.png
   :width: 6mm
   :alt: +

.. figure:: _static/tutorial_add_point_ru.png
   :name: tutorial_add_point_pic
   :align: center
   :width: 20cm

Появится всплывающее окно, где вы можете задать значения атрибутов, например количество парковочных мест - ``15``.

.. figure:: _static/tutorial_add_point_attr_ru.png
   :name: tutorial_add_point_attr_pic
   :align: center
   :width: 20cm

Также доступно две дополнительных вкладки. На вкладке **Описание** можно добавить форматируемый текст и изображения. На вкладке **Вложения** можно прикрепить к объекту любое количество фотографий или других файлов. Перейдите на вкладку "Вложения", нажмите |button_upload| **Загрузить** и выберите файлы ``bike_parking.jpg`` и ``rules.pdf`` из папки с примером.

.. |button_upload| image:: _static/button_upload.png
   :width: 6mm

.. figure:: _static/tutorial_add_attachments_ru.png
   :name: tutorial_add_attachments_pic
   :align: center
   :width: 20cm

Нажмите кнопку **ОК**, чтобы сохранить объект. 

Теперь снова перейдите в контекстное меню слоя *Велопарковки* и нажмите **Завершить редактирование**.

.. figure:: _static/tutorial_stop_edit_ru.png
   :name: tutorial_stop_edit_pic
   :align: center
   :width: 16cm

Подтвердите изменения, нажав кнопку **Сохранить** в появившемся диалоговом окне.

.. figure:: _static/tutorial_edit_confirm_ru.png
   :name: tutorial_edit_confirm_pic
   :align: center
   :width: 12cm

Новый объект создан. 

Кликните по синему кружку, отмечающему точку на карте. Появится панель идентификации, на которой показаны атрибуты объекта, его описание (если есть) и вложения.

.. figure:: _static/tutorial_feature_identify_ru.png
   :name: tutorial_feature_identify_pic
   :align: center
   :width: 20cm

Кликните по прикрепленной фотографии или панораме, чтобы посмотреть их.

Теперь в слое есть данные, и можно опубликовать их с помощью сервиса OGC API Features.

.. _ogc_api:

Публикация сервиса OGC API — Features 
--------------------------------------

Опубликуем слой с помощью протокола OGC API — Features, чтобы его можно было редактировать в сторонних приложениях. Вернитесь в группу *Москва*, нажмите **Создать ресурс** и выберите тип **Сервис OGC API Features**.

.. figure:: _static/tutorial_select_ogcapif_ru.png
   :name: tutorial_select_ogcapif_pic
   :align: center
   :width: 20cm

Всё, что нужно сделать для создания сервиса - выбрать слой.  

На вкладке **Сервис OGC API Features** нажмите |button_plus_layer| **Слой** и выберите слой **Велопарковки*, затем нажмите **Выбрать отмеченное**.

.. figure:: _static/tutorial_ogcapif_select_layer_ru.png
   :name: tutorial_ogcapif_select_layer_pic
   :align: center
   :width: 20cm

По умолчанию ресурс будет называться просто "Сервис OGC API Features". Чтобы задать другое название, перейдите на вкладку **Ресурс** и введите ``Велопарковки - сервис``. Затем нажмите кнопку **Создать**.

.. note:: Название "Велопарковки" уже используется - это название векторного слоя, поэтому нужно добавить слово "сервис" в конце. 

.. figure:: _static/tutorial_ogcapif_name_ru.png
   :name: tutorial_ogcapif_name_pic
   :align: center
   :width: 16cm

Будет создан сервис и откроется его страница. В разделе **Внешний доступ** вы увидите эндпойнт опубликованного сервиса. Скопируйте адрес ссылки, чтобы использовать её в сторонних приложениях.

.. figure:: _static/tutorial_ogcapif_result_ru.png
   :name: tutorial_ogcapif_result_pic
   :align: center
   :width: 16cm

.. _next:

Что дальше
-----------

Поздравляем! Вы закончили туториал и теперь владеете основами управления данными в NextGIS Web.

Однако у нашей платформы ещё много возможностей. Узнайте, как:

* управлять пользователями и правами доступа, настраивать доступ для отдельных слоёв, сервисов и карт;
* управлять системами координат;
* управлять данными из настольного приложения QGIS, публиковать проекты в Веб ГИС, работать со слоями и редактировать данные с нескольких компьютеров одновременно;
* и многое другое.

Попробуйте другие туториалы или читайте подробное описание возможностей платформы в Документации.















