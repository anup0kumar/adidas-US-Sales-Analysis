
# adidas US Sales Analysis-Dashboard

## OverView

A. The Dataset contains details of the adidas product sales in USA across different cities in 2020 and 2021 .
It consist of how many units sold , operating profit, operating margin in different adidas product category and the sale method type i.e whether it is sold online , in-store or through outlets.

B. The Objective of the Analysis is to find insight from the dataset so that the company Know their strength, weakness , opportunity and threats and the potential growth that can be achieved in upcoming years.

C. The four Main BI questions consist of 
- What Happened:- The sales increase 4 times in 2021 in comparison to 2020
- Why did it Happened:- It may be because of corona in 2020 was at peak in USA daily approximately 2 lakhs cases were registered for corona positive. The government ordered is to close all kind of business except medical and Grocery shops were opened only.
- What Will Happen:- As corona affected whole world due to lockdown the sales may not be as expected in 2020 but in 2021 as many country government removed the barrier for market it went up.
- How can we make it Happen:- As the government removed the barrier it helped the company to restart the sales of their product therefore the sales went up exceptionally in 2021 as compared to 2020.
   


### Steps followed 

- Step 1 : Load the data files ("adidas US Sales .xlsx" ) into Power BI Desktop.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options to check the data integrity.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present .
- Step 5 : But the values in total sales was 10 times than the values that should be after multiplying the unit sold and unit price. So divide it by 10 and also for operational profit column.
- Step 6 :Use a line chart to visualize monthly sales trends for both year 2020 and 2021.
- Step 7 : Used a stacked Column chart to analayze the sum of total sales in different region by different retailer
- Step 8 : Visual filters (Slicers) were added for 5 fields named "Region", "Product" ,"City","State" & "Date(in Between)".
- Step 9 : Four card visuals were added to the canvas, one representing sum of total sales, sum of units sold, sum of operating profit & average of operating margin.
           
- Step 10 : Summarize key insights from the dashboard, including top-performing Products , periods of peak sales, 
 
- Step 11 : Calculated column was created  which representing operational margin of the prodcuts at the end of the months.

for creating new column following DAX expression was written;
       
        End Of Month = EOMONTH([Invoice Date], 0)
        
Snap of new calculated column ,

![Snap_1](https://github.com/user-attachments/assets/c86b3f42-461c-42fc-ae31-ea7258657e21)

        
- Step 12 : New measure was created to Avg Of operational Margin.

Following DAX expression was written for the finding the average selling price and for most expensive sku.

        Avg Operational Margin = AVERAGE('Data Sales Adidas'[Operating Margin])

        
A card visual was used to represent sum of Total Sales.

![Snap_Count](https://github.com/user-attachments/assets/10cb682f-0823-48e7-8026-8b58eb6c6bca)

        
 - Step 13 : New measure was created to find  Avg Unit Price,
 
 Following DAX expression was written to find units per view,
 
        Avg Unit Price = DIVIDE(sum('Data Sales Adidas'[Total Sales]),SUM('Data Sales Adidas'[Units Sold]))
 
 A matrix visual was used to represent %sum of total sales, sum of units sold, minimum , maximum & avg unit price of the product .
 
 Snap of the matrix .
 
 ![Snap_Percentage](https://github.com/user-attachments/assets/be51c0b7-8695-4751-9d22-0d809a694dc3)

  Following DAX expression was written to find units per view,
 
        Avg Unit Price = DIVIDE(sum('Data Sales Adidas'[Total Sales]),SUM('Data Sales Adidas'[Units Sold]))

 
 - Step 14 : New Measure was created for the Operational margin target achieved or not at the end or month if not achieved then it will show red dot and if its achieved then it will show green dot.

Following Dax expression was written to identify whether target of 0.40 i.e 40% of operational margin is achieved or not. 

        color switch Rev = 
        VAR var1 = [Avg Operational Margin]
        VAR var2 = [Target Operating Margin]
        VAR result_1 = SWITCH(TRUE(),
        var1 >= var2 , "#145a5a",
        var1 < var2, "#C73040")
        Return result_1
 
 
 # Report Snapshot Page 1 (Power BI DESKTOP)

 
![Dashboard_upload](https://github.com/user-attachments/assets/413e215a-953a-46ae-9544-98aa5375a5f9)

# Report Snapshot Page 2 (power BI Desktop) 

![Dashboard_uploaded](https://github.com/user-attachments/assets/d0cc7efb-d911-4f75-9100-1a8905ebbb97)



# Insights

The company total sales in 2021 is almost 4X than it was in 2020. 
It was because of the following retailers:-

 -  Sports Direct sold 10 times unit sold in 2020.
 -  Foot Locker almost 3times.
 - West Gear almost 2.3times
 - Amazon(New Retailer in 2021) sold 200K units.
The company perform outstanding in west region in both 2020 and 2021 .
IN 2021 company tried to increases sales in Midwest region compared to previous year and also able to achieve a great success in it.
in 2020 sum of total sales in Midwest region was only $737K but in 2021 it was $12.84 million which is approximately 17 times than it was in 2020.

Through slicer for product , region , state we can get the details of the performance of the states and region in details.



# Conclusion
The Company was not able to achieve its monthly target for operational margin i.e 40% in 2020 and it was due to covid 19 pandemic.
the company was able to achieve greater than 40% of operational margin in 2021.
As the company operational margin through online is 46% which is highest in all the provided sales method so company should focus to sell the products online and make better platform and services for online customers.
NOTE:-
This dataset have the values during the pandemic and post Covid 19 pandemic.
 
 
