# Configure callback IDs for ticker boards {#concept_m2n_fy3_52b .concept}

A callback ID in DataV is a parameter a widget sends to other widgets, known as target widgets when it responds to your actions, or when an update is automatically triggered. The parameter is a dynamic variable used to query data that is stored in the target widgets.

## Procedure {#section_vqv_1kk_52b .section}

1.  Click the Ticker Board widget and select the **Interaction** tab on the right-side of the panel.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15584088149296_en-US.png)

    **Note:** In DataV version 4.0, you can configure a callback ID in both the Interaction and Style tabs.

2.  Select the **Enable** check box on the right side of **Trigger Event when Number Changed**.
3.  Under the **Bind to a Variable** column, change value to income as shown in the following example, so that other widgets can use the income variable to retrieve this parameter.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15584088159297_en-US.png)

    **Note:** With this feature, you can configure different variable names for different widgets to make it easier to differentiate between parameters.

4.  You can use `:Variable name` \(such as `:income`\) in the data source, as shown in the following example:

    -   SQL:

        ```
        select :income as value
        select A from table where income = :income
        ```

    -   API:

        ```
        http://api.test?income=:income&amp;id=:myid
        ```

    **Note:** 

    -   Callback ID is not supported if the **Data Source Type** is **static data** or a **CSV file**.
    -   A callback parameter auto-complete feature is available in DataV. Type `:` when you configure the data source to view the names of the variable that are configured in the current project. Press the up and down arrow keys to move through the variables and press **Enter** to select.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15584088159300_en-US.png)


## Advanced settings {#section_id3_bcz_q2b .section}

-   **Set custom fields**

    1.  Click the Data tab.
    2.  Set an id field value to 123.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15584088159298_en-US.png)

    3.  Click the Interaction tab to return to the widget's interaction configurations.
    4.  Click **Create a New Field**.
    5.  Enter id under the **Field** column and enter a variable name under the **Bind to a Variable** column.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15584088159299_en-US.png)

        **Note:** This variable can take effect only when both the **Field** and the **Bind to a Variable** fields are filled out.

-   **Set the default value for the callback ID**

    Set the default value of the callback ID by configuring the request parameters in the URL, as shown in the following example:

    ```
    http://datav.aliyun.com/screen/000000?myid=123
    **Note:** "000000" refers to the screen ID.
    ```

    When accessing data through this URL, the value of the callback ID myid is already set to 123 by default.

    Use the ampersand sign “&amp;” to join multiple callback IDs. The following example sets default values for both callback IDs,myid and income.

    ```
    http://datav.aliyun.com/screen/000000?myid=123&amp;income=1000
    **Note:** "000000" refers to the screen ID.
    ```


