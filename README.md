Business Case: 

The Accounts Department of the Company maintains the invoice level details of all vendors for each part procured. 
The Business Planner receives invoice data from the Accounts Department for each vendor and collects the supplier and part 
level information separately from the Purchase Department. 
The Business Planner has to study the relevant data and identify the Procurement trends, Supplier limitations, Product based supplier consolidation
and minimise cost impact to company.

Problem Statement: 

As the collected Data is of different years for multiple Plants grouped by different Business Units. 
The parts are either made of Aluminium or Ferrous of different raw material grade alloys, with the source being either Tier 1 supplier or Tier 2 supplier.
Considering all these factors, create a dashboard which is insightful on all these factors and can help the Procurement Department make better 
supply chain strategic decisions.

---------------------------------------------------------------------------------------------------------------------------------------------------
Scenario 1
Our task is to build a dashboard page and name it as “Supplier Overview”, which gives us a supplier status and its capabilities.
Also, categorizing them as per the data provided in the data set. This will help the responsible Purchase Group (Buyer) get a focused quick insight for the suppliers.

Scenario 2
We need relevant slicers which would help us understand the data much better, go ahead and plot the below listed columns for slicing.
Also sync the common slicers on both pages
Use the reference Image to decide which slicer goes on which page.

Pur Group (Buyer Code) - Supplier data Table
Supplier Name - Supplier data Table
Part Family - Material Weights and source Table
Plant - Master Report
MCR Material Group - Master Report
Business Unit - Master Report
Commodity - Supplier data Table
Casing and Machining  - Supplier data Table
Now let's put up an additional entry in the Table chart in “Supplier Overview” page, listing the purchase volume (Invoicevalue) of each of the suppliers. 
Use the below reference image and plot the table chart 


Task 5: 

In the “Volume Movement” page, Calculate the tonnage weight per invoice with the help of system weight for each part from the “Material weight and source” table.
Tonnage = (invoice quantity*system weight)/1000

Plot the below mentioned charts

Tonnage vs Supplier Name, name it as “Supplier Tonnage”
Tonnage by Part Family, name it as “Part Family Tonnage”
Tonnage by month distributed by Years, name it as “Tonnage by Month and Year”
Tonnage by RM Grade, name it as “RM Grade Tonnage”

Steps:

Create a DAX calculated column named “Tonnage”using the predefined function LOOKUPVALUE() under the “Master Report” data table.
Reference Link
write a Look-up function to fetch the system weight value from “Material weight and source” table as per the respective UID column.
Once you have the system weight multiply that with the respective quantity, and divide that with 1000 to convert the weight into Tons.
Name this column as Tonnage.
Now use this to plot the requested charts as mentioned in the task and replicate the same as shown below.
![image](https://github.com/sachi21/Power-bi-1/assets/39633676/97a5cc1a-e32a-46d0-8706-1998f957e800)
![image](https://github.com/sachi21/Power-bi-1/assets/39633676/b2380ec9-cca1-4bfd-9b2c-6a8aa3b1f266)

Scenario 3

Let's improve the way our visuals interact with each other with the help of Edit Interactions. 
We would have to change from “Highlight” to “Filter” for each combination pair of visuals, so that it is more clear readability of the data.

Steps:

Select one visual at once and then change the selection from “Highlight” to “Filter” for all other visuals.
Now repeat the same selecting another visual till all of them are covered

![image](https://github.com/sachi21/Power-bi-1/assets/39633676/1e212ae2-5481-49e3-9efc-fd9b02f2ce50)

Task 2: 

As we have a lot of visuals on the “Volume Movement” Page so lets overlap 2 visuals, and with the help of Bookmarks and Buttons make them swappable.

Steps:

Select the Visual of “BU Purchase Volume” and overlap that on “RM Grade Tonnage”, resize both to the same size.
Create a “right arrow” button and place it on top of a visual, as shown below.
![image](https://github.com/sachi21/Power-bi-1/assets/39633676/94f6235f-bfcc-4ff2-9a38-6e016f5344b4)


Use the Selection plane to rearrange the layer of the visual and bring “RM Grade Tonnage” on the top of “BU Purchase Volume”.
Now create a new bookmark, select the shown visual and the right arrow button holding Ctrl button on keyboard. Now ADD a bookmark and name it as “RM Grade Visual”.
Click on the “...” (three dots) of the bookmark and remove the ✔ from “Data”.
Now in the “Selection” tab hide the visual of “RM Grade Tonnage” and the Right Arrow.
Add another Left Arrow Button on top of the visual of “BU Purchase Volume”, as shown below.
![image](https://github.com/sachi21/Power-bi-1/assets/39633676/b585c059-77b1-409d-9ed4-3e692189e9cc)


Please make sure you position both  “BU Purchase Volume” and “RM Grade Visual” on top of each other.
Now repeat the same process of creating another Bookmark named as “BU Visual”.
Once both the bookmarks are ready, click on each of them one by one and check if they are responding correctly. 
If they are not working correctly then use the “hide” option in the selection menu and update the Bookmarks again.
Now Select the right arrow Button and assign an action to it of Type -> Bookmark and Bookmark -> BU Visual.
Now Select the left arrow Button and assign an action to it of Type -> Bookmark and Bookmark -> RM Grade Visual.
Turn On the Button Text option under Format Button option and type the text you want to show.
The Final Result of both swappable views should look like this.


 

Task 3: 

Focusing on the below 2 visuals, as of now we have 2 years of report data added to the master report. 
As the data grows we will have multiple lines for each year drawn in our visual, which will make it difficult to read.

Adapt the Report 2021 data into the master and then change the visual filter so that it only displays the comparison of top 2 years. 
This will help us to always compare the data with the previous year.

![image](https://github.com/sachi21/Power-bi-1/assets/39633676/04ffaa77-688d-47ca-96b5-a162862edefb)
![image](https://github.com/sachi21/Power-bi-1/assets/39633676/983ffdc7-6a87-4514-b5ab-e63f584a3942)



Steps:

In Power Query Editor, add the new source and select the Report 2021 data file and import it
Select Report 2021 and correct the data types of each column.
Now select Master Report dataset, in the right box of “Applied Steps” click on the gear icon next to source, 
change the selection from “Two tables” to “Three or more tables” and then add the Report 2021 to “ Tables to append”
Now we have 3 years of data, and as you can see there are 3 data colour lines.
Select either of the visuals, and go to the “Filters” banner on the right side next to “Visualizations” banner.
In there look for the “Year” Card (if not found drag and drop it), then change the filter type to from “Basic filtering” to “Top N” and 
set it as Top 2 and in the By value field drag and drop the “Year” column and change it to “First Year”from the selection. Click on the apply filter.
Now plot a slicer with a date column, and change the type of slicer to “Before”. Try sliding the date slider to the end of 2020. And see how the data lines 
change from 2020 & 2021 to 2019 & 2020.
Now repeat the same process for the other area chart.
This way whenever we use this specific date slicer and reduce the timeline, power BI will take the top 2 year values and show the data for those years.
![image](https://github.com/sachi21/Power-bi-1/assets/39633676/05652232-4e44-4909-8d42-9b91b7decc3c)
![image](https://github.com/sachi21/Power-bi-1/assets/39633676/bcab5372-d867-462b-a6e0-458de5e65555)



Task 4: 

Lets create a tooltip to get more exposure to the relevant data. The tooltip must contain Tonnage of  RM Grade with its casting source. As shown Below 

![image](https://github.com/sachi21/Power-bi-1/assets/39633676/2529f4f9-67bc-4dde-8edd-5abbc1fab312)


Reference Video - Link https://www.youtube.com/watch?v=URTA7JZsAtw

Steps:

Add a new page, Turn on Tooltip under page information and change the page size type to “Tooltip” and rename the page as RM.
Now add the first visual distributing tonnage by RM Grade.
And then add another one visual distributing tonnage by Casting Source.
Expand both visuals and use the overall page size.
Now reduce the text size to minimum so that it can fit the maximum text in it.
Now go back to the “Volume movement” page and select “Invoice value distribution per supplier” visual and change the tooltip for it.
Turn on the Tooltip option under the Format option, change the type to “Report page” and select the page as “RM”.
Now it's done, you’ll be able to see the tooltip created by you everytime you hover over this visual.











