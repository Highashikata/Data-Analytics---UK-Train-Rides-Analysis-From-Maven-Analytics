# Data-Analytics---UK-Train-Rides-Analysis-From-Maven-Analytics

This is a project to apply some of Power BI knowledge to a Maven Analytics problem.

### Data Source.
In this project, we will download data from Maven Analytics website, this is the link to explore all their Datasets: [Maven Analytics Datasets](https://www.mavenanalytics.io/data-playground?order=date_added%2Cdesc&search=uk&tags=Business).


### Details
UK Train Rides
Mock train ticket data for National Rail in the UK, from Jan to Apr 2024, including details on the type of ticket, the date & time for each journey, the departure & arrival stations, the ticket price, and more.

Recommended Analysis
- What are the most popular routes?

- What are the peak travel times?

- How does revenue vary by ticket types and classes?

- What is the on-time performance? What are the main contributing factors?

### Designing the Report Mockup.
Before diving into the developpement of our, we will be using the following Website [MOKKUP AI](https://app.mokkup.ai/screen/88451), in order to design our Report mockup.

### Data Modeling
After the step of data transformation, the next step is Data Modeling, we begin by identifying the diffrent Fact and Dim tables and we need to also verify the different relationships between Facts and Dims in order to see the consistency of these relations.
This is the first look of our Data Model.

<div align="center">
  <img width="287" alt="image" src="https://github.com/user-attachments/assets/3d9638f2-947b-4dc9-bc8d-8c034f20ccc0" />
</div>


### Data Model optimization
In every Power BI project, when we try to analyze our data and track the eveolution in time, we need to create a Calendar table, it's one of the best practices.

```
Calendrier = 
VAR StartDate =
    MIN ( Fact_railway[Date of Purchase] )
VAR EndDate =
    MAX ( Fact_railway[Date of Purchase] )
VAR DateTable =
    ADDCOLUMNS (
        CALENDAR ( StartDate, EndDate ),
        "QuarterNo", QUARTER ( [Date] ),
        "QuarterName", FORMAT ( [Date], "\QQ" ),
        "MonthNo", MONTH ( [Date] ),
        "MonthName", FORMAT ( [Date], "MMM" )
    )
RETURN
    DateTable
```

Then, we've created our different measures and put them into the 'Mesures' table.

<div align="center">
  <img width="509" alt="image" src="https://github.com/user-attachments/assets/97b77503-b54f-494f-b7f1-c63c8fa91f83" />
</div>



### Report Development
Canvas settings : Custom 1100 x 1500 px.
Colors:
- BG: #F2F2F2.
- Gradient Color: #1F5B73 (as a max) and #F2F2F2 (as a min).


### Final  report View.

![Demo GIF](https://github.com/user-attachments/assets/268e7e46-f142-4730-923c-c00b18c6eb05)


  
