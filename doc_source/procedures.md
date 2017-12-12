# Finding Prices in an Offer File<a name="procedures"></a>

You can use the offer files to find the prices and terms for a specific product\. For example, you can find a list of Amazon EC2 instance prices\.

The following procedures show how to find Amazon EC2 products by downloading an offer file as a CSV or JSON file and sorting the results\.

**To find an EC2 Reserved Instance using the CSV file**

1. Download the EC2 CSV file\.

1. Open the CSV file with your program of choice\. For this example, we use Excel\.

1. Select all cells in the Excel spreadsheet\.

1. In the navigation bar of the spreadsheet, choose **Data**\.

1. In the **Data** bar, choose **Sort**\.

1. In the **Sort by** dropdown list, choose column **TermType**, and then choose **OK**\.

1. Scroll down until you find the value `reserved` in the **TermType** column\. Products that are marked `reserved` in the **TermType** column have reserved rate pricing\.

**To find an EC2 Reserved Instance using the JSON file**

1. Download the JSON file\.

1. Open the JSON file with your program of choice\. For this example, we use Notepad\+\+\.

1. Press CRTL\+F\.

1. For **Find what**, type *reserved*\.

1. Choose **Find All in Current Document**\.

The **reserved** search results open in a new pane at the bottom of the window\.