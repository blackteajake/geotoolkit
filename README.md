# geotoolkit
收集那些有用的、好用的与地理数据管理、地理空间分析、地图相关的工具和项目。



# GeoJson

- <http://geojson.io>：在浏览器地图中，编辑和预览geojson。可以很方便在地图上面添加点、路线、多边形等feature，并对feature设置属性，最终的geojson可导出，如图：

  <img src="images/geojson_io.png" style="zoom: 33%;" />

- [geojsonio-cli：](https://github.com/mapbox/geojsonio-cli) 命令行工具，通过参数指定geojson文件，调起geojson.io网页并加载geojson数据。对不大的geojson文件，可生成一个链接用于分享，别人点开这个链接将在浏览器里自动打开 <http://geojson.io> 预览这个数据

- [togeojson](https://github.com/mapbox/togeojson)：将kml转成geojson，跟geojson命令行工具合起来用，可实现在地图中预览kml的效果：```togeojson foo.kml | geojsonio```

- [geojson-vt](https://github.com/mapbox/geojson-vt)：将geojson转换成矢量瓦片，C++版本：[geojson-vt-cpp](https://github.com/mapbox/geojson-vt-cpp)

-  [geojson-area](https://github.com/mapbox/geojson-area)：计算geojson里polygon和multipolygon的面积，命令行工具：[geojson-area cli](https://github.com/scisco/area) 

- [tippecanoe](https://github.com/mapbox/tippecanoe)：mapbox出品，可基于大型的geojson数据集一次构建多个zoom（地图缩放等级）的矢量瓦片

- <https://mapshaper.org>：在浏览器里可视化编辑geojson等数据，与geojosn.io不同的是，它不显地图，但它包含了很棒的抽稀工具、命令行交互，最终效果可以导出geojson等格式。



# DB

OSDBs在许多时候都受到了广泛的关注， 其中MySQL，PostgreSQL，Ingres，Firebird以及MaxDB最为流行； 如果你想在空间数据开发中使用开源数据库的话， 目前有三种选择：MySQL、PostGIS与SpatiaLite。 每一种都有其优点及缺点，没有哪种选择是适合所有情况的， 而且每种数据库，可能会有其特有的扩展方法。 

- OGC的地理信息实施规范：OGC下的SFSQL的目的在于定义一个SQL模式以通过一个SQL调用级接口来支持数据集的存储、检索、查询和更新。 地理特征是与地球上某地点相关的真实世界现象的一个抽象，具有空间和非空间属性。 空间属性为几何值，而非空间属性为SQL数据类型值。OGC SQL几何类型的组织结构为一个层次类型，如图6.1所示。 根类型，命名为几何，其类型包括点，线，面以及几何集。 几何集为一个多种几何对象的集合。 多点(MultiPoint)、多线(MultiCurve)以及多面(MultiSurface)是几何集管理多种点集、线集和面集的一个专用的亚类型。在OGC SFSQL版本1.2.0中， SQL功能被定义为已知类型文本描述或者二进制描述的条件下构建上述类型的实例， SQL/MM几何方法被用作定义意思类型的SQL功能的参考。

- [SpatiaLite](https://www.gaia-gis.it/fossil/libspatialite/index)：它是从SQLite扩展而来的，支持使用SQL来操作地理空间数据，作用类似 PostgreSQL + PostGIS 的意思，SpatiaLite很多方面都是依照PostGIS， 包装了相应的[GEOS](https://trac.osgeo.org/geos/)库函数，可以使用SQL进行包含几何类型关系计算相关的复杂查询。官方cookbook：https://www.gaia-gis.it/gaia-sins/spatialite-cookbook-5/index.html

- [GeoPackage](https://www.geopackage.org/)： 一种开放的、基于标准的、独立于平台的、可移植的、自描述的、紧凑的格式，用于存储和传输地理空间信息。主要特性是使用SQLite来存储地图瓦片、feature、feature索引，并且实现了读写接口，非常适合于离线场景和移动端使用。库和工具列表：http://ngageoint.github.io/GeoPackage/ 、http://www.geopackage.org/implementations.html，其中移动端的demo和SDK见：GeoPackage MapCache 和 GeoPackage Mobile。
- 

# 算法

- [simplify-geojson](https://github.com/maxogden/simplify-geojson)：使用道格拉斯-普克算法，对geojson里的线、多边形轮廓进行抽稀，用较少的点来近似表示一条原本较平滑的路径，命令示例：```cat data.geojson | simplify-geojson -t 0.01```
- <https://proj.org/>：地图投影坐标系之间的转换。
- [GEOS](https://trac.osgeo.org/geos/)：是“Geometry Engine, Open Source”的缩写，是一个集合形状的拓扑关系操作实用库，简单得说，就是判断两个几何形状之间关系和对两个几何形状进行操作以形成新的几何形状的库。它提供了OGC规范中简单几何要素对象操作的C++语言的实现。



# Tile

* [tippecanoe](https://github.com/mapbox/tippecanoe)：基于大量的GeoJson构建矢量瓦片集。
* 



# 综合

- <http://turfjs.org/>：Advanced geospatial analysis for browsers and Node.js