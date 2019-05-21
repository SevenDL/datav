# Manage your workspaces {#concept_axh_m4k_bhb .concept}

This topic describes how to use the workspace management function of DataV to manage different projects and user permissions between different projects. Each workspace corresponds to a DataV console.

## Use workspaces {#section_kyr_fr4_p2b .section}

1.  Log on to the .
2.  Log on to the .
3.  Log on to the [DataV console](https://partners-intl.console.aliyun.com/#/datav).
4.  From the **Default Workspace** drop-down list in the upper-right corner of the page, select **Workspace Management**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136649/155843466740657_en-US.png)

5.  Create and configure a workspace.

    On the Workspaces page, you can manage workspaces. Specifically, you can switch, create, view, rename, or delete a workspace as needed. For detailed information, see [Manage workspaces](#section_g2z_qr4_p2b).

    After you create and configure a workspace, you can return to the DataV console and refresh the console page.

    **Note:** After you refresh the console page for the first time, the default workspace is displayed.

6.  Select a workspace from the **Default Workspace** drop-down list and switch between workspaces.

    You can also copy projects from one workspace to another. For detailed information, see [Copy a project to the other workspace](#section_bpr_k4q_bhb).


## Manage workspaces {#section_g2z_qr4_p2b .section}

On the Workspaces page, you can:

-   Switch between different workspaces by clicking the workspace name.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136649/155843466740690_en-US.png)

-   Create a workspace by following these steps:

    **Note:** By default, the Basic Edition of DataV provides one workspace, the Enterprise Edition allows you to create one workspace, and the Developer Edition allows you to create four workspaces.

    1.  Click **+** on the right of **My Workspace**.
    2.  Enter the following information:
        -   **Name**: Enter a name for the workspace.

            **Note:** The workspace name must be unique.

        -   **Project Quota**: Click **+** or **–**, or enter a value to adjust the project quota.

            **Note:** The Enterprise Edition allows you to create 20 projects, and the Developer Edition allows you to create 40 projects.

        -   **Favorite Quota**: Click **+** or **–**, or enter a value to adjust the quota of your favorite projects.

            **Note:** The Enterprise Edition allows you to add 20 projects to your favorites, and the Developer Edition allows you to add 40 projects to your favorites.

    3.  Finish or cancel creating the workspace.
        -   To finish creating the workspace, click **Create**.
        -   To cancel creating the workspace, click **Cancel**.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136649/155843466740669_en-US.png)

-   View and configure a workspace. Click the name of a workspace and configure the workspace by following these steps:
    -   Configure the basic information about the workspace.

        Click **+** or **–**, or enter a value to set the **Project Quota** and **Favorite Quota**.

    -   Manage workspace members.

        The permissions of different members are as follows.

        ![Permissions of workspace members](images/40947_en-US.png)

        -   Add a RAM administrator. In the **Administrator** field, enter the username or the ID of the target RAM user and click **Add**.
        -   Add a RAM developer. In the **Developer** field, enter the username or the ID of the target RAM user and click **Add**.
        -   Delete a workspace member. In the member list, locate the target workspace member and click the **Delete** icon.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136649/155843466740670_en-US.png)

    -   Rename a workspace. Move the pointer over the workspace name and click the **Edit** icon.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136649/155843466740671_en-US.png)

    -   **Note:** Once a workspace is deleted, it cannot be recovered.

        Delete a workspace. Move the pointer over the workspace name and click the **Delete** icon.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136649/155843466740672_en-US.png)

        **Note:** Only the Alibaba Cloud account administrator has the permission to delete a workspace. Before the administrator deletes a workspace, make sure the workspace does not have any projects, data sources, groups, or favorite widgets.


## Copy a project to the other workspace {#section_bpr_k4q_bhb .section}

In the DataV console, you can copy a project from a workspace to another workspace by following these steps:

1.  Move the pointer over the target project and click **Copy to Workspace**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136649/155843466740694_en-US.png)

2.  Select the target workspace and click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136649/155843466740699_en-US.png)

3.  Switch to the target workspace and view the project that you have copied.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136649/155843466740700_en-US.png)


