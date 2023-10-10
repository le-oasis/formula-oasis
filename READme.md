# Modern Data Engineering: Building a Data Lakehouse with Apache Spark - Vol 2.

## Overview

- Welcome to Volume 2 of our two-part series on Data Engineering, where we dive deeper into the practical aspects of building a Data Lakehouse using Apache Spark. 

- In Volume 1, we introduced you to the concept of Data Lakehouse architecture and set up the Integrated Development Environment (IDE), Gitpod, for our project. 

- In this volume, we will focus on configuring services within our Data Engineering ecosystem to enable seamless communication between them. Additionally, we will guide you on how to create templates to implement your own data projects, proofs-of-concept, and tests on the platform.


## Prerequisite
Before you proceed with Volume 2, it's essential to have completed Volume 1, where we laid the groundwork for this series. If you haven't done so already, please refer to Volume 1 Readme for an overview of the concepts discussed.

## Data Source

In Volume 2, we will be using a Formula One dataset from ergast.com as our sample data source. This dataset provides comprehensive information about Formula One races, drivers, teams, and more. Before we dive into how we ingest this data into our Data Lakehouse, let's briefly explain the dataset:

As mentioned earlier, the Formula One dataset consists of several files, including CSV and JSON formats, which provide comprehensive information about Formula One races, drivers, teams, and more. The files and their corresponding descriptions are as follows:

- `circuits.csv`: Data about Formula One circuits.
- `constructors.json`: Information about constructors (teams).
- `drivers.json`: Details about Formula One drivers.
- `pit_stops.json`: Records of pit stops during races.
- `races.csv`: Information regarding Formula One races.
- `results.json`: Race results data.
- `lap_times/`: A folder containing lap times data for races.
- `qualifying/`: A folder containing qualifying data for races.

## Manual Data Upload to Amazon S3

To manually upload the Formula One dataset to our Amazon S3 bucket (`oasiscorp-raw/formula-oasis`), we followed these steps:

1. **Access Amazon S3**: Log in to your AWS Management Console and navigate to the Amazon S3 service.

2. **Create a Bucket**: If you haven't already created the `oasiscorp-raw` bucket, you can do so by clicking the "Create bucket" button. Follow the prompts to configure your bucket settings. Ensure that it is in the appropriate region and has the desired access permissions.

3. **Upload Files**: Inside the `oasiscorp-raw` bucket, create a folder named `formula-oasis`. This folder will serve as the root directory for storing our Formula One dataset. Then, upload the following files to this folder:
   - `circuits.csv`
   - `constructors.json`
   - `drivers.json`
   - `pit_stops.json`
   - `races.csv`
   - `results.json`

4. **Upload Folder**: For the `lap_times` and `qualifying` data, you can create separate folders within `formula-oasis` and upload the contents of the corresponding folders there.


## Using the CLI 

To upload the Formula One dataset to our Amazon S3 bucket using the AWS CLI, we followed these steps:

1. **Install the AWS CLI**: If you haven't already installed the AWS CLI, you can do so by following the instructions provided in the [AWS CLI documentation](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html).
2. **Configure the AWS CLI**: Once you have installed the AWS CLI, you can configure it by running the `aws configure` command. Follow the prompts to enter your AWS Access Key ID, AWS Secret Access Key, and default region name. 
3. **Upload Files**: To upload the files to your S3 bucket, you can use the `aws s3 cp` command. For example, to upload the `circuits.csv` file to the `oasiscorp-raw/formula-oasis` bucket, you can run the following command:

```bash
aws s3 cp ~/Downloads/data/raw s3://oasiscorp-raw/formula-oasis/ –recursive
```


## Data Lakehouse Storage

Once the data is uploaded to Amazon S3, you can configure your Data Lakehouse to access and process this data. Amazon S3 is a scalable and durable object storage service, making it an ideal choice for storing large datasets like the Formula One dataset.

In your Data Lakehouse environment, you can set up the necessary connectors and configurations to access and query the data stored in your S3 bucket. You can use tools like Apache Spark, AWS Glue, or other data processing frameworks to work with this data effectively.

Now that you have successfully ingested the Formula One dataset into your Data Lakehouse, you can proceed with the data processing and analysis steps outlined in Volume 2 of our series. This includes configuring the services within your Data Engineering ecosystem and using Apache Spark to derive valuable insights from the data.

Feel free to refer to the provided code examples and templates in Volume 2 to streamline your data processing workflows. Happy data engineering!
