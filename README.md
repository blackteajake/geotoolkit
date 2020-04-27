# geotoolkit
收集那些有用的、好用的与地理数据管理、地理空间分析、地图相关的工具和项目。



# geojson

- <http://geojson.io>：可在浏览器地图中，编辑和预览geojson，geojson可导入和导出。如图：

  ![](images/geojson_io.png)

- [geojsonio-cli：](https://github.com/mapbox/geojsonio-cli) 命令行工具，通过参数指定geojson文件，调起geojson.io网页并加载geojson数据。对不大的geojson文件，可生成一个链接用于分享，别人点开这个链接将在浏览器里自动打开 <http://geojson.io> 预览这个数据。

- [togeojson](https://github.com/mapbox/togeojson)：将kml转成geojson，跟geojson命令行工具合起来用，可实现在地图中预览kml的效果：```togeojson foo.kml | geojsonio```

