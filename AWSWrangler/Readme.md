Using AWS data wrangler to integrate with the source. 
This can connect to most of the AWS resources as per the docs : https://github.com/awslabs/aws-data-wrangler

For this use case we want to:
  1. Create a front end which can take input from the end user 
    1.1. Plug the value into the sql query in the backend
    1.2. Execute the query and then give the result as a dataframe
    1.3. Convert the dataframe into a CSV file and store in AWS
    1.4. Athena must read the same and generate a DDL automatically using a crawler
    1.4. Quicksight needs to automatically update the result of the query and make use of filters for further analysis
    
  2. Create an dynamic editable table based on the dataframe.
    2.1. This dataframe will then be sent back to AWS s3 bucket as a CSV
    2.2. This CSV can be crawled using Athena and automaically generate the DDL
    2.3. This should be read from Quicksight
  
