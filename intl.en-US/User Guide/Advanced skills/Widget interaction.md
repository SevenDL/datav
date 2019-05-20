# Widget interaction {#concept_pbb_2vk_q2b .concept}

Widgets can interact with each other through related callback IDs, see [Configure widget interaction](reseller.en-US/User Guide/Manage widgets/Configure widget interaction.md#). By using callback IDs, if you click a widget, data of a widget with the corresponding callback ID will change accordingly.

Using a timeline widget as an example, with a callback ID, after you click a timestamp the map widget displays detailed information of this timestamp, see [Configure widget interaction](reseller.en-US/User Guide/Manage widgets/Configure widget interaction.md#).

![](images/8532_en-US.gif)

## Set a callback ID {#section_ef1_p35_q2b .section}

A callback ID can be considered as a parameter variable that is used to control the transmission of parameters between widgets, and realize interactions between them \(that is, if data of one widget is updated, other widgets with the same callback ID are also updated\).

**Note:** Callback ID is not supported if the Data Source Type is Static Data or a CSV file.

For instance, if you click a scattered point in a map, click a row in a list, or select a time point on a time table, the system temporarily stores the designated callback ID, for example, name, into the name variable.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16584/15583432498533_en-US.png)

## Set variable input {#section_i5q_535_q2b .section}

When the Data Source Type is SQL or API, you can directly input the variable.

```
select :name as value
select A from table where year = :name
```

If you are using an API data source, the system directly assigns value to the variable parameters with the same name.

