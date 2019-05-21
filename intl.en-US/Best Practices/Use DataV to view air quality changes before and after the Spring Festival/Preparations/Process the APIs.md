# Process the APIs {#concept_lgr_rtq_p2b .concept}

This topic describes how to change data on the isosurface layer with the timeline. An API or a database is needed to obtain data from different monitoring sites during different periods of time.

We recommend that you write an API.

-   Request address: /aqi
-   Request method: GET
-   Request parameter:
    -   Parameter: date
    -   Parameter type: string, for example, 2017012722. The format is YYYYmmDDHH.

1.  Process all the downloaded data. Node.js provides a glob module to process all data in the directory in batches.

    ```
    var fs = require('fs');
    var csv = require("fast-csv");
    var glob = require('glob');
    var mapdata = require('. /Longitude and latitude mapping in the site list.json');
    glob(". /Site_20170101-20170202/*.csv", function (err, files) {
    files.forEach(function (file) {
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
    });
    });
    ```

    The result is as follows.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17464/15584087069273_en-US.png)

2.  Use the glob module to integrate the data. Use the file name \(which is a date\) as the key, and the corresponding content as the value. Then, you will obtain an integration file named all.json.

    ```
    //The following method is not suitable to process data in large scale.
    var fs = require('fs');
    var csv = require("fast-csv");
    var glob = require('glob');
    glob("./data/*.json", function (err, files) {
    var datas = {};
    files.forEach(function (file) {
     var filename = file.replace(/^. *[\\\/]/, '').split('.')[0];
     datas[filename] = require(file);
    });
    fs.writeFile('./data/all.json', JSON.stringify(datas));
    console.log('done');
    });
    ```

3.  Use the express framework of Node.js to initialize an express project, and add an API according to the preceding API requirements.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17464/15584087079274_en-US.png)

    **Note:** To avoid cross-domain requests, you can add a cors module to the app.js file.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17464/15584087079275_en-US.png)

4.  After processing the API, run the npm start command to test the API.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17464/15584087079276_en-US.png)


