# Configure widget interaction {#concept_xmk_kjt_q2b .concept}

## Procedure {#section_id3_bcz_q2b .section}

The following example uses a Ticker Board widget.

1.  Select a Ticker Board widget, and then click the Interaction tab on the right side of the page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16580/15583457178601_en-US.png)

2.  In the upper-right corner of the **Trigger Event when Number Changes** menu, select **Enable**.
3.  Change the variable name listed under the Bind to a Variable column. As shown in the following example, `value` is changed to `income`.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16580/15583457178604_en-US.png)

    Other widgets can use the variable named income to retrieve this parameter.

    **Note:** With this feature, you can configure different variable names for different widgets, so as to differentiate used parameters.

4.  You can use `:Variable name` \(such as, :income\) in the data source, as shown in the following example:

    -   SQL:

        ```
        select :income as value
        select A from table where income = :income
        ```

    -   API:

        ```
        http://api.test?income=:income&id=:myid
        ```

    **Note:** 

    -   If you select **Static Data** or **CSV file** from the **Data Source Type** drop-down list, a callback ID is not supported.
    -   DataV supports callback parameter auto-complete. When configuring a data source, if you type `:`, the editor prompts all variable names that were configured in the current project. Use the up and down arrow buttons to browse the variables and press **Enter** to select. The callback parameter auto-complete feature helps you easily view any previously configured variables so that you can better navigate your widgets and data.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16580/15583457178607_en-US.png)


## Advanced settings {#section_ify_3dw_y2b .section}

-   **Set custom fields**

    1.  Click the Data tab of the Ticker Board configuration pane.
    2.  Configure a id field , and the value is 123 at the data source section.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16580/15583457178605_en-US.png)

    3.  Click the Interaction tab.
    4.  Click **Create a New Field**.
    5.  Enter an id in the **Field** column and enter a variable name under the **Bind to Variable** column.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16580/15583457178606_en-US.png)

        **Note:** Only when both the **Field** and the **Bind to a Variable** fields are filled out, can this variable take effect..

-   **Set the default value for the callback ID**

    Set the default value of the callback ID by configuring the request parameters in the URL, as shown in the following example:

    ```
    http://datav.aliyun.com/screen/000000?myid=123
    **Note:** "000000" refers to the screen ID.
    ```

    When accessing data through this URL, the value of the callback ID `myid` is already set to **123**.

    Use the ampersand mark \(&\) to join multiple callback IDs. The following example sets default values for both callback IDs, `myid` and `income`.

    ```
    http://datav.aliyun.com/screen/000000?myid=123&income=1000
    **Note:** "000000" refers to the screen ID.
    ```


