.. sectionauthor:: Артём Светлов <@nextgis.ru>

.. sxf:

Работа стека NextGIS с форматом sxf
=====================================

Введение
----------------------------

В этой инструкции мы возьмём геоданные в формате sxf, загрузим их в NextGIS Web, настроим их стиль отображения, и отобразим их на веб-карте. 
Для работы потребуется:


#. Набор данных в формате sxf - скачайте выгрузку из Openstreetmap на странице http://www.gisinfo.ru/price/price_map.htm
#. :program:`NextGIS QGIS`.
#. Доступ к инстансу :program:`NextGISWEB`. - у вас должен быть его URL, логин и пароль.


Подготовка sxf к загрузке
----------------------------

Скачайте на странице http://www.gisinfo.ru/price/price_map.htm выгрузку данных OpenStreetMap на любой интересующий вас регион.

.. figure:: _static/sxfDownloadSample.png
   :name: sxfDownloadSample
   :align: center
   :scale: 30 %


Распакуйте их в каталог.
Поскольку :program:`NextGISWEB` сейчас поддерживает импорт только из форматов ESRI Shapefile и geojson, то нам нужно сконвертировать sxf в geojson. 

Запустите :program:`NextGIS QGIS`.

Нажмите :menuselection:`Слой --> Добавить слой --> Добавить векторный слой`.


.. figure:: _static/sxfQGISOpenLayerDialog.png
   :name: sxfQGISOpenLayerDialog
   :align: center
   :scale: 30 %

На экране появится диалог выбора слоёв из файла sxf. В этом примере мы загрузим слой железных дорог (Railway) и землепользования (landuse)

.. figure:: _static/sxfQGISOpenSXFLayers.png
   :name: sxfQGISOpenSXFLayers
   :align: center
   :scale: 30 %

Сохраните эти два слоя в формате geojson. Для этого, выделите слой landuse в списке слоёв, нажмите правой кнопкой мыши, и в открывшемся контекстном меню выберите пункт :guilabel:`Сохранить как`.


.. figure:: _static/sxfQGISSaveLayerMenu.png
   :name: sxfQGISSaveLayerMenu
   :align: center
   :scale: 30 %

В диалоге сохранения задайте следующие настройки:

#. Формат - geojson
#. Система координат - EPSG:4326. Если её не будет в предложенном списке (такое бывает при первом запуске программы), то нажмите на кнопочку рядом, и в окне поиска введите "4326".


.. figure:: _static/sxfQGISSaveDialog.png
   :name: sxfQGISSaveDialog
   :align: center
   :scale: 30 %


.. figure:: _static/sxfQGISSearchProjection.png
   :name: sxfQGISSearchProjection
   :align: center
   :scale: 30 %

Сохраните слои как landuse.geojson и railway.geojson.


Загрузка в NextGIS Web
----------------------------------

Откройте в браузере имеющийся у вас адрес инстанса, введите логин и пароль.

Нажмите :guilabel:`Векторный слой`, задайте название "Землепользование".
Перейдите на вкладку :guilabel:`Векторный слой`, нажмите на кнопку, и загрузите файл landuse.geojson.
Нажмите на кнопку :guilabel:`Создать`





