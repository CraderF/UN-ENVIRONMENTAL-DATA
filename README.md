
# UN Environmental Data Analysis
## Project Overview
This project explores key environmental indicators from United Nations datasets, including CO2 emissions, forest cover, and threatened species. Using Python for data manipulation and SQL for querying, the analysis provides insights into trends in global carbon emissions, deforestation, and biodiversity loss over time.

The project demonstrates key data science skills, including data cleaning, exploratory data analysis (EDA), and data visualization, which are crucial for making data-driven decisions in the environmental field.

## Table of Contents
* Project Motivation

* Data Sources

* Technologies Used

* Project Workflow

* Key Findings

* Installation Instructions

* Contributing

* Contact


## Project Motivation
Climate change, deforestation, and species extinction are among the most pressing global environmental issues. Understanding historical trends in carbon emissions, land use, and biodiversity loss is essential for shaping sustainable policies and mitigating environmental impacts. As a father of two beautiful daughters, these issues are extremely pressing. I believe that exploring the data, and show you all the same data, is the key to understanding just how important this is on a global scale.

In this project, the goal is to:

* Analyze and visualize trends in global CO2 emissions from 1975 to 2017.

* Explore changes in global forest cover, threatened species and permanent crop cover. 

* Use SQL and Python for data analysis and visualization.

* I wish to showcase my practical data science skills which are applicable to the environmental sector, particularly in roles related to data analytics, sustainability, and environmental protection.


## Data Sources
The datasets used in this project are from the United Nations Environment Programme (UNEP) and cover:

* CO2 Emissions: Global carbon dioxide emissions data from 1975 to 2017.

* Forest Cover: Data on forest area in various countries over several decades.

* Permanent Crop Cover: Data on permenent crop growth globally. 

* Threatened Species: Information on the number of threatened species worldwide.

* These datasets are publicly available on the UNEP website or through the UN Data Portal.


## Technologies Used
**Python Libraries**:

* pandas for data manipulation.

* NumPy for numerical operations.

* Matplotlib and Plotly for data visualization.

* SQLAlchemy for connecting to and querying SQL databases.

* SQL (mySQL): Used for joining datasets and extracting relevant data for analysis.

* Jupyter Notebook: For code execution and presenting the analysis in an interactive format.

## Project Workflow
**Data Loading**:

* Data is loaded into a SQL Database through mySQL from CSV files. 

* Data is loaded from the SQL database into Python using SQLAlchemy.

**SQL Queries**:

* Join different datasets using SQL to combine CO2 emissions with forest cover and species data.

* Perform data transformations (interpolations, conversions) using Python.

**Data Cleaning**:

* Handle missing values and data type conversions.

* Convert CO2 emissions data into metric tons for consistency.

* Creating 'Year' columns in the combined tables for sorting.

**Exploratory Data Analysis (EDA)**:

* Create visualizations to understand trends in emissions, forest cover, and threatened species.

## Conclusions:

**Key Findings**
Global CO2 Emissions: From 1975 to 2017, global CO2 emissions increased significantly. This increase was by 18,859,079,393 metric tons of Carbon Dioxide.
Forest Cover: Global deforestation trends continue to cause forest cover to shrink globally. 
Permanent Crop Cover: The increase in permanent crop cover aligns and indicates that it is a major contributor to the declining forest cover.
Biodiversity Loss: There is a clear correlation between declining forest cover and an increase in the number of threatened species, indicating the need for integrated conservation efforts.
These insights represent the beginning of our understanding of these interconnected issues and provide a glimpse into the real data provided by the United Nations. This data serves as a wake-up call for us all, showing the critical need for immediate action. We must take steps, however small, to address these pressing challenges and work towards a more sustainable future.

## Installation Instructions
To run this project locally, follow these steps:

Clone the Repository:

* git clone https://github.com/CraderF/UN-Environmental-Data-Analysis.git

Navigate to the Project Directory:

* cd UN-Environmental-Data-Analysis

Install the Required Python Libraries: You can install the required dependencies using pip:

* pip install -r requirements.txt

Run the Jupyter Notebook: Start Jupyter Notebook and open the UN_ENVIRONMENTAL_DATA.ipynb file:

* jupyter notebook
  
Run the Analysis: Execute the cells in the notebook to run the full analysis and see the visualizations.

## Contributing

If you'd like to contribute, please fork the repository and make any changes you'd like. Pull requests are always welcome.

## Contact
Feel free to reach out if you have any questions or feedback:

### Felix Crader

**Email**: felixcrader@gmail.com

**LinkedIn**: www.linkedin.com/in/felixcrader

**GitHub**: https://github.com/CraderF 

