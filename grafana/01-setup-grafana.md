# Setup Grafana

Installing Grafana on a Windows Server is a straightforward process. Here’s a step-by-step guide to help you set up Grafana on your Windows Server:

### Step 1: Download Grafana

1. **Go to the Grafana Download Page**:

   - Visit the [Grafana Download Page](https://grafana.com/grafana/download).
2. **Download for Windows**:

   - Click on the **“Windows”** tab and download the latest stable version. It will usually be a `.zip` file.

### Step 2: Install Grafana

1. **Extract the Zip File**:

   - Extract the downloaded `.zip` file to a suitable directory (e.g., `C:\Program Files\Grafana`).
2. **Navigate to the Grafana Folder**:

   - Go to the extracted folder and open the **`bin`** folder.
3. **Start Grafana**:

   - Double-click on the **`grafana-server.exe`** file to run it.
   - You should see some information displayed in the command prompt, indicating that Grafana is running.

### Step 3: Set Up Grafana as a Service (Optional)

If you want Grafana to run as a Windows service, follow these steps:

1. **Download NSSM (Non-Sucking Service Manager)**:

   - NSSM is a service manager for Windows. You can download it from the [official NSSM website](https://nssm.cc/download).
2. **Install NSSM**:

   - Extract the downloaded file to a suitable directory (e.g., `C:\nssm`).
3. **Add Grafana as a Service Using NSSM**:

   - Open the command prompt as an administrator.
   - Run the following command:
     ```bash
     C:\nssm\nssm.exe install Grafana
     ```
   - In the window that opens, enter the following:
     - **Path**: `C:\Program Files\Grafana\bin\grafana-server.exe`
     - **Startup directory**: `C:\Program Files\Grafana\bin`
   - Click the **“Install service”** button.
4. **Start the Grafana Service**:

   - In the same command prompt, run the following command:
     ```bash
     nssm start Grafana
     ```

### Step 4: Access Grafana

1. **Open Your Web Browser**:

   - Launch your web browser and navigate to `http://localhost:3000`.
2. **Log In**:

   - Use the default username and password:
     - **Username**: `admin`
     - **Password**: `admin`
   - You will be prompted to change the password on your first login.

### Step 5: Add a Data Source

1. **Add Data Source**:

   - Click on the gear icon (⚙️) in the left menu and go to **“Data Sources.”**
   - Click the **“Add data source”** button.
2. **Choose Your Data Source**:

   - Select the data source you want to use (for example, **Prometheus**).
3. **Configure the Data Source**:

   - Enter the necessary configuration settings for your chosen data source (e.g., URL, authentication, etc.).
   - Click the **“Save & Test”** button to test the connection.

### Step 6: Create a Dashboard

1. **Create a New Dashboard**:

   - Click on the plus icon (➕) in the left sidebar and select **“Dashboard.”**
2. **Add a Panel**:

   - Click on the **“Add new panel”** button and select your data source.
3. **Write a Query and Visualize**:

   - Write the appropriate query for your metrics and configure the panel settings.
   - Adjust the visualization options and save the panel.

### Conclusion

By following these steps, you can easily install Grafana on a Windows Server. After completing the installation, you can add your data sources and create custom dashboards. Leverage Grafana’s powerful visualization and monitoring features to effectively monitor your systems. Enjoy your Grafana setup!
