<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Visualize Data with QuickSight

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-analytics-quicksight)  
**Author:** Michael Nelms  
**Email:** michaelj.nelms@gmail.com

---

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-analytics-quicksight_6c7f7ef0)

---

## Introducing Today's Project!

This project was designed to help me learn how to visualize structured data using **Amazon QuickSight** — AWS's business intelligence and analytics service. The experience gave me practical exposure to setting up datasets, integrating S3 data sources, and creating interactive dashboards.

### Tools and concepts

I used **Amazon S3** to store the dataset and **Amazon QuickSight** for data ingestion, analysis, and visualization. Key concepts I learned include:
- Creating an S3 bucket
- Structuring and referencing a `manifest.json` file
- Connecting external data to QuickSight
- Building visual dashboards from CSV data
- Updating datasets and refreshing insights

### Project reflection

This project took approximately 20 minutes to complete. The most challenging part was refining the visualizations to best represent the insights I wanted to highlight. Getting the right combination of filters and chart types required some experimentation. 

After completing this project, my next focus will be exploring IAM permissions and access control to better secure analytics workflows.

---

## Upload Project Files into S3

Amazon S3 was used to host the two required project files:
- `netflix_titles.csv`: the main dataset
- `manifest.json`: a file that tells QuickSight how to locate and interpret the dataset

I modified the `manifest.json` file to include the direct S3 URI for the `netflix_titles.csv`. This step is important because QuickSight uses the manifest to properly map the data source during import.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-analytics-quicksight_3c3cd85a)

---

## Create QuickSight Account

I created a new QuickSight account using the **standard edition's free trial**, which provided enough functionality for this project.

The account setup process was straightforward and took only 1–2 minutes to complete through the AWS Console.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-analytics-quicksight_f4ab4214)

---

## Download the Dataset

To connect the dataset to QuickSight:
- I navigated to the S3 bucket
- Copied the direct URL to the `manifest.json` file
- Used that URL inside QuickSight to ingest the dataset

The `manifest.json` plays a crucial role because it tells QuickSight the exact location and structure of the data file. Without it, QuickSight wouldn’t know how to process the CSV properly.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-analytics-quicksight_6f874996)

---

## My First Visualization

To build my first visualization in QuickSight:
- I selected a **bar chart** to visualize trends
- Dragged and dropped the `release_year` and `type` fields into the visual editor

The chart breaks down Netflix releases by year and categorizes them by type: TV Shows, Movies, or Other. The intuitive drag-and-drop UI made it easy to build meaningful visuals from raw CSV data.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-analytics-quicksight_aff3aad7)

---

## Using Filters

I applied filters to refine the dataset and isolate specific segments. For example, I focused on content types (TV Shows vs. Movies) over a defined release period to compare content volume over time.

Filters are powerful for slicing and dicing large datasets and help surface insights that would otherwise be lost in the noise.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-analytics-quicksight_c32248c5)

---

## Setting Up a Dashboard

To organize and present my visualizations:
- I renamed each chart for clarity
- Grouped related charts together into a cohesive dashboard

QuickSight also allows dashboards to be **exported as PDFs**, which I tested by publishing the dashboard and exporting it. This makes it easy to share findings with stakeholders or in documentation.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-analytics-quicksight_6c7f7ef0)

---

## Refreshing Source Data

To simulate working with updated or real-time data:
- I downloaded an updated version of the dataset with new entries
- Uploaded both the new CSV and an updated `manifest.json` file to my S3 bucket

Initially, QuickSight didn’t reflect the updated data. To resolve this, I:
- Went to the dataset in QuickSight
- Selected **Edit Dataset**
- Manually refreshed the data
- Saved and republished the analysis

This part reinforced how QuickSight handles data refreshes and how critical it is to maintain correct file paths and metadata.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-analytics-quicksight_86415f4e3)

---

