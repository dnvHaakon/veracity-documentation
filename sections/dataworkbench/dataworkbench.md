---
author: Veracity
description: This page contains an overview of Data Workbench.
---
# What is Data Workbench?
Data Workbench allows you to:
* Get access to data and use it in your applications.
* Securely share your data and use data shared by others.
* Monitor who uses your data and revoke access to it.
* Build dashboards and reports on top of the data.
* Work with scalable data streams and self-defined non-time-series data streams.

## Tenants and workspaces

Each company or a B2C customer has one tenant in Data Workbench. A tenant can have multiple workspaces. Each workspace has members. Workspace members can be admins or readers. For information on user management, go [here](usermanagement.md).

### To create a new workspace
If you are a tenant admin, you can use the picker button to create a new workspace:
1. In the upper-left corner of the "Home" page, select the workspace and tenant picker button.
2. In the dropdown that appears, at the bottom, select the **Add workspace** button.

## Connectors and connections
 Data Workbench fetches data from external data sources by using connectors. A connector:
* Is an integration layer between a data provider and the Data Workbench. 
* Uses an API exposed by the provider to query data, and transforms it into a unified format used in Data Workbench.
* Is authorized on the provider's side and follows their authorization policy.
* If the provider enables downloading binary data, a connector stores this data into cloud file stores, so that it can used by customers.

A connection binds together a connector and a tenant's workspace, and it is used by the data set to query data from a data source. 

To see available connectors and connections in your workspace, go to the **Connections** tab. 
Once you have a connection set up, the Data Catalogue will show the predefined data sets queried from the corresponding source system.

### Become a data provider
To become a data provider and integrate with Data Workbench, contact the Data Workbench team for assistance.

To integrate, you will need to implement a standardized API that consists of mandatory and optional endpoints that cover REST API verbs, paths, and contracts for request and response payloads.

Note that:
* The API allows only the REST protocol.
* You need to host the API in your own environment.
* You need to allow Data Workbench to access this API. If you have a firewall, adjust the rules accordingly.

The Data Workbench team will cooperate with you on gathering the requirements for creating a connector. Expect to discuss:
* Technical aspects for server-to-server communication such as base URL of your API, server-to-server API keys, and more.
* Schemas that should be supported by the connector. Data Workbench queries data for a certain schema, and your API also needs the schema to decide how to satisfy the request.
* Custom settings for each schema.
* Definition of settings that must be provided with a new connection.

Also, you need to create connections. Currently, the Data Workbench team does it for you, but Veracity plans to make it self service.

### Data restrictions
Data Workbench can impose restricions on access to data. For each connector, Veracity can configure a definition of mandatory settings that its connections must follow. These settings are represented by a dictionary (string<=>string) meaning they can contain any data (authorization data, environment data, etc). 

## Data sets
To see data sets available in your workspace, go to the **Data Catalogue** tab. 

The **Predefined data sets** tab shows data sets that are queried by connections from their corresponding source systems. These data sets are inherited, and you cannot modify them. However, you can use them to create new data sets.

The **Created data sets** tab shows the data sets that workspace members created.

For each data set, in the top right corner, you can select the following action icons.
1. Data set info - see data set name and its description.
2. Edit table properties - disable or enable column picker and select what data columns to show.
3. Filter - apply and clear the filters available for the data set.
4. Save - **Save** the current view of the data set (including applied filters and shown columns) or **Save as new** to create a new data set with the applied filters and shown data columns.
5. Download - download the data set as a CSV file.
6. Share - share the data set with someone else.
7. Delete - if you are an admin, delete the data set.

 Note that, depending on your [user role](usermanagement.md), you might not see some icons.

<figure>
	<img src="assets/dataseticons2.png"/>
	<figcaption>Action icons for data sets.</figcaption>
</figure>

### Types of data sets
Data sets can be saved and shared as:
* **Data live streams (dynamic)** dynamic - when there is a change in a data set, it gets automatically updated.

### To create a data set
To create a derived data set:
1. Select an existing data set.
2. Apply filters to get relevant data.
3. Save the data set.

Veracity suggests using an existing template for creating your data sets. The templates are shown in the **Home** tab under the navigation menu. Note that a template can contain one or more data sets.

To create a new data set from a template:
1. In the **Home** tab, select a template.
2. If there is more than one data set in the template, select a data set.
2. In the right corner, select the **Save as new** icon and save a copy of the data set.
3. Edit the data set to suit your needs. Consider using "Edit table properties" (the pencil icon) and filters (the three vertical lines icon).
4. Optionally, to download the data set from as a CSV file, in the right corner, select the **Download** icon.


### To upload a data set from a CSV file
If you are an [admin](usermanagement.md), you can upload a data set from a CSV file.

To upload a data set from a CSV file:
1. In the **Data catalogue** tab, in the top right corner, select **Upload data set**. A pop-up window will appear.
2. In the window, add a CSV file by draging and dropping it or selecting it from your drive. You can add only one file.
3. In the **Data set name**, define the data set name and, in the **Description**, add its description.
4. To upload the data set created from the CSV file, select the **Upload** button.

Note that now you have created a data set you can share with other users.

### To share a data set
You can share a dynamic (live) version of a data set to file storage in [Data Fabric](https://developer.veracity.com/docs/section/datafabric/datafabric) and specify who can access it.

To share a data set with one or more users:
1. Hover over the row with a data set. Action icons will appear in the right corner of the row.
2. Select the **Share** icon.
3. Under **Share with user**, enter the email address of a user. You can add multiple users.
4. Select the **Add** button to confirm.
5. Select the **Share** button. 

Note that:
* Users are notified by email when they get access to a data set.
* If you try to share a data set with an email account that is not registered with Veracity, Veracity will show the **Invite** button. If you select it, Veracity will invite this person to register, and they must register in Veracity to get access to the data set you have shared with them.

Alternatively:
1. Go to a data set you want to share.
2. In the top-right corner, select the **Share** icon.
3. Under **Share with user**, enter the email address of a user. You can add multiple users.
4. Select the **Add** button to confirm.
5. Select the **Share** button. 

### To see data sets shared with you
To see the data sets that have been shared with you:
1. From the main page of Data Workbench, go to **Recent data sets** and then select **See all data sets**.
2. Go to the **Shared with me** tab.

Alternatively:
1. Go to the **Data Catalogue** tab.
2. Go to the **Shared with me** tab.

Note that you cannot edit data sets that are shared with you.

### To revoke access to a data set
To revoke access to a data set:
1. Go to the data set.
2. Go to the **Details** tab.
3. Under **Shared with**, select the pencil icon. A pop-up window with the list of users will appear.
4. In the row with the user's name, to revoke their access, select the **X** icon. After that, the icon changes to the "Undo" icon. If you have revoked user's access by accident, select the "Undo" icon to revert it.
5. Select the **Save and Close** button.

When you revoke a user's access to a data set, they are notified about that by email.

Alternatively:
1. Go to **Data Catalogue** and select the tab with the data set you want to revoke access to.
2. In the row with the data set, under the **Shared with** column, select a user avatar. A pop-up window with the list of users will appear.
3. In the row with the user's name, to revoke their access, select the **X** icon. After that, the icon changes to the "Undo" icon. If you have revoked user's access by accident, select the "Undo" icon to revert it.
4. Select the **Save and Close** button.


## Activity logs
Data Workbench logs certain events, and gives you access to [activity logs](activitylog.md).
