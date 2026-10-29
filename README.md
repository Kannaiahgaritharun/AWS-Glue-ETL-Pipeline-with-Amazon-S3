# AWS Glue ETL Pipeline with Amazon S3

## 📌 Project Overview

This project demonstrates an end-to-end ETL (Extract, Transform, Load) pipeline using Amazon S3 and AWS Glue. Employee data is uploaded to Amazon S3, discovered using an AWS Glue Crawler, registered in the Glue Data Catalog, transformed using AWS Glue Visual ETL, and stored in an S3 curated data folder.

## 🎯 Objectives

- Store raw employee data in Amazon S3.
- Automatically discover the dataset schema using AWS Glue Crawler.
- Create database and table metadata in AWS Glue Data Catalog.
- Transform employee data using AWS Glue Visual ETL.
- Store processed data in a curated S3 location.

## 🏗️ Architecture

```text
Employee CSV File
       |
       v
Amazon S3 (Raw Data)
       |
       v
AWS Glue Crawler
       |
       v
AWS Glue Data Catalog
       |
       v
AWS Glue Visual ETL
       |
       v
Data Transformation
       |
       v
Amazon S3 (Curated Data)
```

## 🛠️ AWS Services Used

| Service | Purpose |
|---|---|
| Amazon S3 | Stores raw and processed datasets |
| AWS Glue Crawler | Discovers the CSV schema |
| AWS Glue Data Catalog | Stores database and table metadata |
| AWS Glue Visual ETL | Performs data transformations |
| AWS IAM | Manages access permissions |

## 📂 Project Structure

```text
aws-glue-etl-pipeline-amazon-s3/
│
├── README.md
├── data/
│   └── employees.csv
└── screenshots/
    ├── s3-raw-data.png
    ├── glue-crawler.png
    ├── data-catalog.png
    ├── visual-etl-job.png
    └── s3-curated-data.png
```

## 📊 Dataset Details

The input file is `employees.csv`.

| Column | Description |
|---|---|
| employee_id | Unique employee identifier |
| name | Employee name |
| department | Employee department |
| salary | Employee salary |
| city | Employee city |

### Sample Data

| employee_id | name | department | salary | city |
|---:|---|---|---:|---|
| 101 | Rahul | IT | 55000 | Bengaluru |
| 102 | Priya | HR | 48000 | Hyderabad |
| 103 | Arun | Finance | 62000 | Chennai |
| 104 | Meena | IT | 58000 | Mumbai |
| 105 | Kiran | Sales | 45000 | Pune |

## ⚙️ Implementation Steps

1. Created an Amazon S3 bucket.
2. Uploaded `employees.csv` to the `raw/` folder.
3. Created the AWS Glue database `glue_training_db`.
4. Configured and ran the Glue Crawler to discover the employee dataset.
5. Registered the employee table in the Glue Data Catalog.
6. Created a Glue Visual ETL job using the catalog table as the source.
7. Applied the Drop Fields transformation to remove the `city` column.
8. Configured Amazon S3 as the target and selected CSV output.
9. Ran the ETL job and verified the output in the `curated/` folder.

## 📁 Expected Output

The curated dataset contains the following columns:

```text
employee_id, name, department, salary
```

The transformed data is stored in the Amazon S3 `curated/` folder.

## 🔐 Security

- Keep S3 buckets private.
- Use IAM roles with least-privilege permissions.
- Grant the Glue job access only to the required S3 locations and Data Catalog resources.
- Never upload AWS access keys, secret keys, or other credentials to GitHub.

## 📸 Screenshots

Add your AWS console screenshots to the `screenshots/` folder to demonstrate:

- Raw employee data in Amazon S3.
- Successful AWS Glue Crawler execution.
- Employee table in the Glue Data Catalog.
- Visual ETL workflow.
- Transformed output in the curated S3 folder.

## 🎓 Learning Outcomes

- Understanding cloud-based ETL pipelines.
- Working with Amazon S3 storage.
- Using AWS Glue Crawlers and the Data Catalog.
- Performing visual data transformations.
- Managing AWS permissions using IAM.
- Organizing raw and curated datasets.

## 👨‍💻 Author

**Kannaiahgari Tharun**

GitHub: [Kannaiahgaritharun](https://github.com/Kannaiahgaritharun)

---

⭐ This project was developed for hands-on practice with AWS data engineering services.
