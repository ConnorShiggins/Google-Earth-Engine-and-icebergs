# Google-Earth-Engine-and-icebergs

# **Quick introduction**

This code uses ArcticDEM (version 3) 2-meter strip data to automatically detect icebergs in Google Earth Engine (GEE).

This tool was designed to allow users with no coding experience to generate their own dataset of icebergs through a graphical user interface (GUI). Iceberg detection is based on a threshold above sea level with 1.5 m being the default value. However, larger glaciers which calve large icebergs and have dense fjord cover (e.g. Sermeq Kujalleq: Jakobshavn Isbræ) require a greater threshold value to detect icebergs (3.0 m above sea level) and have been validated. To change the default threshold value, a user can easily navigate in the GEE code editor to line 147 and change the 'var icebergDetectionElevation = ee.Number(1.5)' parameter to the required value. Kangiata Nunaata Sermia and Umiammakku Isbræ's icebergs have been validated on a 1.5 m above sea level threshold and Sermeq Kujalleq (Jakobshavn Isbræ) on a 3.0 m value.

All the user needs to do to attain this dataset is define a region of interest (ROI) and click a few buttons for the data to export to their Google Drive!

To be able to use this GUI, a user needs to ensure they have a GEE account (free for individual license). If you do not have an account yet, you can register for one here: https://earthengine.google.com/new_signup/. The authentication process could take a few days to approve the license.

The GUI can be found here: https://code.earthengine.google.com/f38494aa9f268cf807cdefe8c107783e 

Below is a quick run through of how best to use the GUI and attain the data which is required. 

# **Using the tool**

### **Step 1)** 
Once the GUI is accessed through the link above, the GEE browser will open up as shown below (and click 'New Project'):

![homepage](https://user-images.githubusercontent.com/63847501/183452712-b48e22b9-ae8d-4be4-8ca7-0672714face4.PNG)

### **Step 2)** 
A new project has now started so you can now navigate to your glacier of choice (in this example we are using KNS on the southwest coast of Greenland). Draw your ROI before clicking 'OK': 

![ROi](https://user-images.githubusercontent.com/63847501/183454614-b2fed269-2cb6-4669-a9a2-4017b0371808.PNG)

### **Step 3)** 
You may wish to define a date range for your data, but with ArcticDEM data being temporally limited it is suggested to 'OK' the default range provided: 

![Date](https://user-images.githubusercontent.com/63847501/183455053-80332e28-f08b-4b79-9490-0159728e8c06.PNG)

### **Step 4)**
Now the data will load to the map where: 1) the first ArcticDEM scene in the collection will load and 2) the detected iceberg binary image will overlay so the data can be visualised. Hit the export button in the bottom right of the GUI to prompt a task.

![binary](https://user-images.githubusercontent.com/63847501/183455527-d95bec9d-6555-49a9-b92b-dd4b637abd09.PNG)

### **Step 5)**
The dataset has now been generated, however you have not exported the data yet! A warning bar will appear once the export button has been clicked on the GUI, diverting the user to the 'Tasks' bar (highlighted by the orange colour on the top right of the console). You then need to navigate to the task bar: 

![Task bar](https://user-images.githubusercontent.com/63847501/183456239-5b7d8d1d-a9bf-44a7-bdd9-a8f8702756ff.PNG)

### **Step 6)** 
Once the 'Tasks' bar has been selected, press the 'RUN' button next to the 'Iceberg_dataset_file': 

![Run](https://user-images.githubusercontent.com/63847501/183456545-88c29797-b3b5-4a2f-bce6-9c99eea2540a.PNG)

### **Step 7)** 
The 'RUN' button then prompts the Task to export the data to your Google Drive. You can choose to change the default task name, drive folder name and filename itself. If working across different glaciers, it would be sensible to name the iceberg dataset after the respective glacier. The default file format is Shapefile ('SHP'), but you can choose other formats which you see fit: 

![Export](https://user-images.githubusercontent.com/63847501/183457864-e202779e-71de-45c6-9a0a-e105b517e744.PNG)

And that's it! You have your iceberg dataset. All you have to do now is navigate to your Google Drive and whatever you named your 'Drive folder', the data will appear in there!

## **Potential error due to lack of data availability**

Below is a typical error which may arise from this code will be shown. This error may arise because of the spatial limitation of ArcticDEM in the near-terminus regions of Greenland's outlets. This means 1) your defined ROI is too large or 2) no data exists for the glacier in question. To start the project again to try both solutions, just hit the 'Run' bar at the top and a new project will launch. It is suggested to keep your ROI limited in close proximity to the ice front as fjord wide analysis has not been validated because of the lack of spatial data extent. 

![Error](https://user-images.githubusercontent.com/63847501/183460747-32c2da06-c1bb-43b6-9ada-917a3de9cf25.PNG)

Happy iceberging and if you have any questions regarding the tool, please contact Connor Shiggins (Connor.Shiggins@Liverpool.ac.uk)


