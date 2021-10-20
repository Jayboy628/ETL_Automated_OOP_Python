# PLEASE NOTE THE PROJECT IS ONLY 30% COMPLETED. BY END OF WEEK OCTOBER 13 COMPLETE DATE

# OOP - "Automate ETL process using Python and AWS"

![contract](Images/data_python.png)

## My Background

My name is Shaunjay Brown and I have years of experience in Business Intelligence and Data Analysis. Data extraction is one of my many functions in BI and I mainly used SSIS and SQL to Extract Transform and Load. However, I find that SSIS is better suited for large functions like data migration because SSIS has a high overhead cost with maintenance, performance and more importantly time consuming.
I am very excited for my new love for python and using pandas with python allows me to quickly profile the data and quickly decide what I need for my reports.
I am going to illustrate a production ready ETL pipeline in python using Pandas tool to write python code and Visual studio to refactorize the code into an object oriented code.

## Project Background

The Deutsche Börse Public Dataset (PDS) project makes near-time data derived from Deutsche Börse's trading systems available to the public for free. This is the first time that such detailed financial market data has been shared freely and continually from the source provider.

This data is provided on a minute-by-minute basis and aggregated from the Xetra and Eurex engines, which comprise a variety of equities, funds and derivative securities. The PDS contains details for on a per security level, detailing trading activity by minute including the high, low, first and last prices within the time period.

## Content

- Preconfig
  - Set up virtual Environment
  - Set up AWS
- Quick and Dirty Approach - Pandas.

- Functional Approach - Pandas.

- Object Oriented Approach - Visual Studio.

## Files

### Quick and Dirty Approach

- [`access_xetra_data.ipynb`](Starter-Code/accessing_the_xetra_data.ipynb) -- Level 1 Project AWS Connect to Deutsche AWS .

- [`quick_etl_solution.ipynb`](Starter-Code/quick_etl_solution.ipynb) -- Level 2 starter code.

### Reengineer Quick Approach to Funtional

- [`access_xetra_data.ipynb`](Starter-Code/AssociateProfitSplitter.ipynb) -- Level 1 starter code.

- [`quick_etl_solution.ipynb`](Starter-Code/TieredProfitSplitter.ipynb) -- Level 2 starter code.

### Production - Objection Oriented Programming

- [`access_xetra_data.ipynb`](Starter-Code/AssociateProfitSplitter.ipynb) -- Level 1 starter code.

- [`quick_etl_solution.ipynb`](Starter-Code/TieredProfitSplitter.ipynb) -- Level 2 starter code.

## Task Background

![Source Report](Images/xetra_report_src.png)

Above is a sample of the data set as an example, the first columnists, the ISIN the
International Securities Identification Number, each entry of an ISIN shows basic information such as the security type and security ID. The StartPrice, MaxPrice, MinPrice EndPrce and shows how many trade volumes and the number of trades.

The case study shows that our client requirements would like to implement a report that is looking like this.

![Weekly Report](Images/xetra_wkly_report.png)

Here we see an aggregation of the ISI ends on a daily basis and what we want to know are the opening,closing, minimum and maximum price, the daily traded volume and the change of the current day's closing price compared to the previous trading days

Our task now is to create a production ready python data job that is extracting, the source xetra dataset data set from the xetra as S3 buckets since the last run of the job and saves the report in the
target S3 bucket

Above

This project has four levels of difficulty, with each design increasing in complexity and capability. Each level is critical to the overall project and is recommended to complete all four levels.

However before we start coding we need to implement a few

### Preconfig

#### Set up virtual Environment

    * Virtual Environment -> virtualenv
    * pip
    * setuptools
    * wheel
    * pandas

#### Set up AWS

    * AWS account or register an account for free
    * IAM -> Users -> Add User (create a nane)-> Access type (Programmatic access)
      - Attach existing policies -> Filter police (s3) -> AmazonS3Full Access -> create user
      - Download the CSV file -> Acces Key Id and Secret access key
    * Add Access Key Id and Secret Access key to the environment variables

#### Install AWS CLI

    * open your environment -> (Mac) source ~/.bash_profile or (Windows) pipenv shell
    * mac -> pip3 install awscli windows -> pipenv install awscli
    * Type aws configure and Acces Key Id and Secret access key.. see below

![Weekly Report](Images/aws_configure.png) \* Test connection with the your account and Deutche.. see below
![Weekly Report](Images/aws_deutche1.png)

---

### Step one: Quick and Dirty

- **Level One** `access_the_xetra_data.ipynb`. The goal of this python pandas code is to quickly connect to
  the project AWS S3 bucket and pull data from Deutshce Boerse AWS S3 bucket.. see below

  ![Weekly Report](Images/accessing.png)

- **Level Two** is a `quick_xetra_etl.ipynb` This illustrate

  ![Weekly Report](Images/variables.png)

### Step two: Reengineer Quick Approach to Funtional

### Step three: Objection Oriented Programming

### Step four: Finalizing ETL Job

### Requirements

<details>
<summary>Tools and Package</summary>

- Python 3.9
- Jupyter Notebook
- Github
- Visual Studio
- pandas, boto3, pyyaml, awscli, jupyter, pylint, moto, coverage, memory-profile

</details>

<details>
<summary>Python Code</summary>

- Target format parquet
- First date for the report
- Auto-detection of the source files to be processed
- Configurable production-ready Python job

<details>
<summary>Best Practice Python</summary>

#### Best practices in developing Python code

- Design Princples
- Clean Coding
- Virtual Environments
- Configuration
- Logging
- Folder setup
- Unit Testing
- Exception Handling
- Lintig

© 2021 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
