# Process data {#concept_sbr_ss3_52b .concept}

In this example, the CSV files are converted into JSON files.

The following is an example of the data format required by the isosurface layer widget. You need to process the data to better meet the requirements.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17463/15584086839272_en-US.png)

-   **Clip GeoJSON data**: boundary data of the research area. Here the research area covers the whole of China, and the data is in GeoJSON format.

    GeoJSON is an open standard format designed for representing simple geographical features. For more information, see [GeoJSON standards](http://geojson.org/geojson-spec.html?spm=5176.100239.blogcont69319.29.kb5QDK).

-   **Interpolation Points Data**: an array that includes the longitude, latitude, and value of a monitoring site.

To create an isosurface map for a period of time in a day, for example, an air quality index \(AQI\) map at 12:00 on January 20, 2017, you need to obtain the position data \(longitude and latitude\) and the corresponding AQI of each monitoring site. To process data, follow these steps:

1.  Use the following node scripts to process the CSV files:

    ```
    var csv = require("fast-csv");
    var fs = require('fs');
    var map = {};
    csv
    .fromPath(". /Site list (including the longitudes and latitudes)-new-1497.csv", { headers: true, objectMode: true })
    .on("data", function (data) {
     map[data['code']] = data;
    })
    .on("end", function () {
     fs.writeFile('. /Longitude and latitude mapping in the site list.json', JSON.stringify(map));
     console.log("done");
    });
    ```

    A dictionary is obtained. In the dictionary, the monitoring site No. is the key and the site information is the value.

    ```
    {
     "1001A": {
         "code": "1001A",
         "name": "Wanshouxigong",
         "city": "Beijing",
         "lng": "116.366",
         "lat": "39.8673"
     },
     "1002A": {
         "code": "1002A",
         "name": "Dingling",
         "city": "Beijing",
         "lng": "116.17",
         "lat": "40.2865"
     },
     "1003A": {
         "code": "1003A",
         "name": "Dongsi",
         "city": "Beijing",
         "lng": "116.434",
         "lat": "39.9522"
     },
     ...
    }
    ```

2.  Process data obtained from 1,497 monitoring sites on January 20, 2017.

    Use the following scripts to process the AQI data obtained within 24 hours from each monitoring site. Extract the data and add the longitudes and latitudes to the sites according to the longitude and latitude mapping list.

    ```
    var fs = require('fs');
    var csv = require("fast-csv");
    var mapdata = require('. /Longitude and latitude mapping in the site list.json');
    var file = '. /Site_20170101-20170202/china_sites_20170120.csv';
    var filename = file.replace(/^. *[\\\/]/, '').split('.')[0] .split('_')[2];
    var datas = {};
    csv
    .fromPath(file, { headers: true, objectMode: true })
    .on("data", function (data) {
     if (data.type === 'AQI') {
       datas[data.hour] = [];
       for (var key in data) {
         if (mapdata[key]) {
           datas[data.hour].push({
             name: mapdata[key].name,
             value: +data[key],
             code: mapdata[key].code,
             city: mapdata[key].city,
             lng: +mapdata[key].lng,
             lat: +mapdata[key].lat
           })
         }
       }
     }
    })
    .on("end", function () {
     fs.writeFile('./data/' + filename + '.json', JSON.stringify(datas));
     console.log("done");
    });
    ```

    Use the period of time for each day as the key, and the array as the value. The array contains the AQI information and position of each monitoring site of the corresponding periods. Then the data of each period of time for each day can be used in the **isosurface layer** widget.

    ```
    {
    "0": [{ "name": "Wanshouxigong", "value": 18, "code": "1001A", "city": "Beijing", "lng": 116.366, "lat": 39.8673 }, { "name": "Dingling", "value": 25, "code": "1002A", "city": "Beijing", "lng": 116.17, "lat": 40.2865 }, ...],
    "1": [{ "name": "Wanshouxigong", "value": 28, "code": "1001A", "city": "Beijing", "lng": 116.366, "lat": 39.8673 }, { "name": "Dingling", "value": 65, "code": "1002A", "city": "Beijing", "lng": 116.17, "lat": 40.2865 }, ...],
    "2": [{ "name": "Wanshouxigong", "value": 88, "code": "1001A", "city": "Beijing", "lng": 116.366, "lat": 39.8673 }, { "name": "Dingling", "value": 95, "code": "1002A", "city": "Beijing", "lng": 116.17, "lat": 40.2865 }, ...]
     ...
    }
    ```


