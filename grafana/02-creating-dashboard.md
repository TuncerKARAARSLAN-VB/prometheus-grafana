# Creating Dashboard

Creating dashboards in Grafana is a crucial step in visualizing your data and monitoring your systems effectively. Here’s a detailed step-by-step guide to help you through the process of creating dashboards in Grafana:

### Step 4: Creating Dashboards

#### 4.1 Create a New Dashboard

1. **Access the Dashboard Creation Interface**:

   - Open your Grafana instance in a web browser (e.g., `http://localhost:3000`).
   - After logging in, look for the **plus icon (➕)** in the left sidebar. This icon is used for adding new elements within Grafana.

   ![Plus Icon](https://grafana.com/docs/grafana/latest/media/dashboard/add-dashboard-icon.png)
2. **Select "Dashboard"**:

   - Click on the plus icon, and a dropdown menu will appear.
   - From the dropdown menu, select **“Dashboard”**. This action will create a new blank dashboard for you to work with.

   ![New Dashboard](https://grafana.com/docs/grafana/latest/media/dashboard/add-new-dashboard.png)

#### 4.2 Add a Panel

1. **Open the Panel Editor**:

   - In the newly created dashboard, you’ll see a button labeled **“Add new panel”**. Click on this button to open the panel editor.

   ![Add New Panel](https://grafana.com/docs/grafana/latest/media/dashboard/add-panel-button.png)
2. **Choose Your Data Source**:

   - In the panel editor, you will be prompted to select a **data source**. This is the same data source you configured in the previous step.
   - Click on the dropdown menu under **“Query”**, and select the appropriate data source (e.g., **Prometheus**).

   ![Choose Data Source](https://grafana.com/docs/grafana/latest/media/dashboard/select-data-source.png)

#### 4.3 Configure the Panel

1. **Write a Query**:

   - After selecting your data source, you'll see a text box where you can write your query. The specific syntax will depend on the data source you are using. For Prometheus, you might write a query like:
     ```promql
     rate(http_requests_total[5m])
     ```
   - This query retrieves the rate of HTTP requests over the last 5 minutes.
2. **Choose Visualization Options**:

   - Below the query section, you'll find visualization options. Click on the **"Visualization"** tab in the right-hand panel.
   - Choose how you want the data to be displayed. Grafana offers various visualization types, including:
     - **Time Series Graph**: Best for showing data over time.
     - **Stat Panel**: Displays single numeric values.
     - **Gauge**: Good for showing progress toward a goal.
     - **Table**: Displays data in a tabular format.
     - **Bar Gauge**: Shows the value compared to a set range.

   ![Select Visualization](https://grafana.com/docs/grafana/latest/media/dashboard/panel-editor-visualization.png)
3. **Adjust Panel Settings**:

   - **Title**: Click on the title area and enter a meaningful name for your panel (e.g., "HTTP Requests Rate").
   - **Axes**: Configure the X and Y axes settings, which include setting titles, units (e.g., requests/second), and ranges.
   - **Legend**: Enable or disable the legend as needed. Customize its position, and which metrics to display.

   ![Panel Settings](https://grafana.com/docs/grafana/latest/media/dashboard/panel-editor-settings.png)

#### 4.4 Save the Dashboard

1. **Save Your Work**:

   - After configuring your panel, look for the **disk icon (💾)** in the upper right corner of the screen. Click this icon to save your dashboard.

   ![Save Dashboard](https://grafana.com/docs/grafana/latest/media/dashboard/save-dashboard.png)
2. **Provide a Name**:

   - A prompt will appear asking for the name of your dashboard. Enter a descriptive name (e.g., "Web Application Monitoring").
   - If you want to organize your dashboards, you can also choose to save them into folders. Grafana allows you to create and manage folders for better organization.
3. **Finalize the Save**:

   - Click the **“Save”** button after entering the dashboard name. Your dashboard is now saved and can be accessed anytime from the Grafana interface.

   ![Dashboard Name](https://grafana.com/docs/grafana/latest/media/dashboard/dashboard-name-dialog.png)

### Additional Tips

- **Edit Panels**: You can always go back and edit your panels. Hover over a panel, click on the **pencil icon** (✏️) that appears in the top right corner, and adjust your settings.
- **Duplicating Panels**: If you have similar panels to create, you can duplicate an existing panel by clicking on the **panel title** and selecting **“Duplicate”**.
- **Dashboard Settings**: You can access overall dashboard settings by clicking on the **gear icon** (⚙️) at the top of the dashboard to manage layout, permissions, and other settings.
- **Sharing Dashboards**: You can share your dashboard with others. Click on the **share icon** (🔗) at the top, which provides options to share a link, export the dashboard, or embed it.

### Conclusion

Creating dashboards in Grafana allows you to visualize your data effectively. By following these steps, you can set up a dashboard tailored to your monitoring needs. With the ability to create multiple panels and customize them, you can gain valuable insights into your systems, applications, and services. Happy monitoring!
