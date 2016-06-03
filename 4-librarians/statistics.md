#Statistics

##Gate Count

- We use an electronic gate counter that is Velcroed to the wall next to the front doors.  The gate counter is from Sensource, and to troubleshoot any problems, the website is www.sensource.biz.  We have a battery powered sensor, PC-TB12-R.  Replace batteries once a year.
- The box on the right side of the door is the one you take off and attach to the laptop for the gate count. The software for it is on the laptop. The cord to connect the laptop to the Counter is in one of the front pockets of the laptop case. 
- Connect the Counter to the laptop and open the counter software. The software is called USB Download Utility. It should be pinned to the taskbar.  The icon looks like a teal square with a black S in the background and the letters SU in white. 
- Using USB Download Utility:
  - Click Scan for Devices.
  - It should be on Auto Detect and click Download.
  - Nothing will happen for a little bit, don’t worry, it is doing stuff.
  - When it is done downloading a Save As screen will pop up.  Instead of pressing Save, press Exit.
  - Go to the Data tab, select Show All Data.
  - Go to File, select Print.
  - In the Preview window, go to File.
  - Hover over Export Document, select XLSX file.
  - Select ok
  - For File Name enter the date.  Save to the Laptop’s desktop in a folder called Door Count Data.
- Put the counter back, wave your hand in front of the sensor to make sure it is counting properly.
- Copy the file you just created to a flash drive and open it on your computer.
- There will be hashtags for Columns C and D make them wider to view the information, but we are really only using the numbers from Column C.
- Go to J:\FBC General\Stats\Daily Gate Count YEAR.
- Snap this file to one side of the screen, the gate count you opened before to the other side
- On the bottom tabs of the Daily Gate Count YEAR Spreadsheet, go to the sheet called DOOR COUNT on the far right and find the last date and time.
- Find the very next time on the dated gate count spreadsheet you just created.
- Select that row and all of the following rows to the end of the counted time and copy them
- Select the first blank cell in the Daily Gate Count Year Spreadsheet and paste them in.
- The cells of the other tabs should auto complete up to the current day and time.
- Move Raw Value A from Column N to Column G for the data you just added to the spreadsheet.  This is to keep the formula working for the spreadsheet.
- Use this data to fill in the sheet for the appropriate month. There should already be a template in each monthly sheet.  All you need to do is fill in the blanks. 
  - Find the first date/time of the month in column C and copy it into the first Date/Time Open cell.  Grab the bottom right corner of the cell and drag it down that column to the end of the month.  The cells in that column should fill with the dates and times open for each day.
  - Find the last date/time of the month in column C and copy it into the first Date/Time Closed cell.  Grab the bottom right corner of the cell and drag it down that column to the end of the month.  The cells in that column should fill with dates and times closed for each day.  
  - Columns D, E and F on the monthly sheet should now auto fill.  Just in case they don’t, the formula for each of the cells/columns is as follows:
  - Column D - `=VLOOKUP(B2, 'DOOR COUNT'!D1485:G100002, 4)`
  - Column E - `=VLOOKUP(C2, 'DOOR COUNT'!D1507:G10002, 4)`
  - Column F - `=(E2-D2)/2`
  - Also if they don’t populate, make sure the dates columns are filled in with dates from the DOOR COUNT sheet that have recurring times each day. 

[Gate Counter Tutorial](http://kb.sensourceinc.com/kb/entry/56/)

##Bibliographic Instruction

- We track a few things with this: date, class taught, time taught, librarian teaching, how many students were in the class, how many requests were made each month, and the total number of hours spent teaching. These stats are recorded In the BI Stats YEAR Spreadsheet (`J:\FBC Staff\FBC General\Stats\BI Stats YEAR`). 
- The spreadsheet keeps totals by month. These are added in monthly.  Paula assigns a librarian to teach it, and records the librarian's initials on the Google LAW Instruction Calendar. The librarian should record the number of students in the class on the Google calendar after the class beside their initials.
- Most of the information is retrieved from the New Instruction Requests Google Spreadsheet.  To get the New Instruction Requests information, you need to log into Google, select Google Drive from the selections provided, and then go to Shared.  The “owner” of the instruction calendar should share it with you, so you can open the spreadsheet for the semester from the list of shared documents.  Each semester a new spreadsheet is created and shared.
- The timestamp column (A) gives you the date requested, so you can add how many were requested for the particular month you are gathering stats for from that column.

##Circulation

We get Circulation stats from Voyager’s Access Reports, located in the Start Menu under Voyager. 
- Double click on the report listed called “1 Ericas circ by location.”  

>> **JUST IN CASE—the SQL code for that is:**

>> `SELECT [start date] AS StartDate, [end date] AS EndDate, Count([Circulation Transactions (Charges)].CHARGE_DATE) AS CountOfCHARGE_DATE, LOCATION.LOCATION_NAME
FROM ((MFHD_ITEM INNER JOIN [Circulation Transactions (Charges)] ON MFHD_ITEM.ITEM_ID = [Circulation Transactions (Charges)].ITEM_ID) INNER JOIN [Item Location] ON [Circulation Transactions (Charges)].ITEM_ID = [Item Location].ITEM_ID) INNER JOIN LOCATION ON [Item Location].LocationID = LOCATION.LOCATION_ID
WHERE ((([Circulation Transactions (Charges)].CHARGE_DATE) Between [start date] And [end date]))
GROUP BY [start date], [end date], LOCATION.LOCATION_NAME
HAVING (((LOCATION.LOCATION_NAME) Like "Fair*"));`

- A pop up dialog box will ask for Start Date and End Date parameters.  Put in the dates using dashes, not slashes.  (5-31-2015)
- The report will take a while to load.  Just wait, it can’t be hurried.
- Once the report appears in the Access window, select all of the cells to copy to an Excel document.
- Copy it to the Circ Stats YEAR workbook.  (J:\FBC Staff\FBC General\Stats\Circ Stats YEAR)

##Reference/Service Transactions

Go to [LibAnswers homepage](http://ivytech.libanswers.com/index.php)

- Log in using your Libguides username and password (for right now, not your LibApps login, your LibGuides login—once we migrate Libanswers to version 2, you will login using your LibApps login).
- On the orange bar at the top, click on the arrow beside the words REF. ANALYTICS and select STATISTICS from the drop down menu.
- You will be on a page that displays all stats for all campuses from 2013 to the present.  To filter your results so that you only see results from your campus, use the Search/filter at the top of the page.
- In Region, select 8
- In Campus, select Lawrence
- In the time period section, select your time period.  I usually do a month, but you can look at stats from 2013 to now, so if you want to look at a year, or 6 months, or a day, you can select the time period you wish to see.
- Then select Search/Filter at the bottom of the filter section
- The results below (and on the other tabs) will display the results you asked for. 
- For the monthly stats, look at the Analyze Metadata tab.
- We usually need the total Transactions, at the top of the Date/Time Stats page, and also a breakdown of where the questions are from.  This data is found in a table called “How was it asked?” 
