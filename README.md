# AMP501_GUI

### Description

This GUI is intended to be used as an additional tool to QA/QC data that has already been put into AQS. In the current Beta version, the GUI can create a site file which allows the user to analyze an entire network. The user can then use the site file and a AQS-generated AMP501 report to perform a "gap analysis". This analysis using the sampling frequency code and duration code to determine if a Null code or valid data point is present for the entire duration of the timeseries being evaluated. This GUI is being developed in order to address inconsistencies in reports that are currently generated by AQS users, and allow for air quality data managers to have a better understanding of the quality of their data.

### Installation
Install this GUI by downloading the most current repository. Once you unzip the file, the application is called "GapGUI_Main_2Frames_v1.exe" in the "...\dist\GapGUI_Main_2Frames_v1\\" folder.

### Usage
Once the program is installed, Use AQS to generate an AMP500 and AMP501 for your network/time period of interest. The AMP500 contains information pertaining to every monitor in the network queried, while the AMP501 contains the raw data from the monitors queried. Examples of the AMP500 and AMP501 have been provided in the "test_data" folder of the repository.

#### Creating a Site File
The Site config file is used to configure which monitors will be analyzed. You must have one in order to run the gap analysis. You do not have to create a new site file every time the gap analysis is run, however.

* Click "Menu", then in the drop-down, click "Create Site File". This will open a new window with all the input parameters for creating a new site file. Click "Choose AMP500 File" to navigate to the input file, or use the text box below the button to type the path by hand.
* In "Time Interval", choose what time period you would like to use monitors from. Enter the text for the start date in the white text box under "Choose Start Date". Note that the date format is the same used for querying data in AQS. Likewise, you can enter the end date in the next white text box below in the same date format.
* In the Output section, click the "Choose Output Filename" button to choose what to name the new site config file, or use the text box below the button to type the path by hand.
* Click "Create Site Config File" to produce the new site config file! Once your site config file is created, exit out of the "Create New Site Config File" window frame.

#### AMP501 Gap Analysis
The Gap analysis allows for a user to determine if there are any gaps in the data that has been uploaded to AQS. This is, there is not a data value or null for each required sampling period of the instrument. Since this code is still in beta version, Particulate FRM data with low sample frequencies may erroneously report gaps are present when they aren't ( certain number of filters required each quarter, instead of a certain temporal frequency).

* In the main home window, choose which site file to use. This can be one you just created, or one created in a previous session. Click "Choose Site File" to navigate to the site config file, or use the text box below the button to type the path by hand.
* Click "Choose AMP501 Input File" to navigate to the input file, or use the text box below the button to type the path by hand.
* This analysis will produce multiple text files corresponding to good (and bad) results of the analysis. Therefore, it would be wise to set aside a specific folder in which the results will be output to. Choose this output folder in the program by clicking "Pick Output Folder", or use the text box below the button to type the path by hand.
* Once all the input file and output directory information has been provided, run the analysis by clicking "Run Gap Analysis!" Once the analysis has successfully completed, a window will pop up with the message "Gap Analysis Complete!". After, you can run more analyses on more datasets, if desired. A command window, which opens with the GUI, will show which monitors were analyzed. A program log is created every time this algorithm is run, which will save the messages which are output to the command window automatically. An additional output file is created for each monitor determined to contain data gaps. The filename corresponds the the monitor's AQS code parameters as follows: "county code+site code _ parameter code _ POC _ gaps _ v1.txt" For example, a POC 1 PM25 monitor (parameter code 88101) at the Bountiful station in Utah (county doe 011, site code 0004) would have the following filename: "0110004_88101_1_gaps_v1.txt"


### Credits
Credit to State of Utah Division of Air Quality, and Lexie Wilson and Kim Kreykes for being my beta testers. 

### License
No current license available
