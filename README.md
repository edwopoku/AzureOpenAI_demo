# Overview

Azure OpenAI is an innovative partnership between Microsoft Azure and OpenAI, created to equip businesses with cutting-edge AI technology. This collaboration offers direct access to OpenAI's advanced language models through the Azure cloud, allowing companies to seamlessly integrate AI-driven insights, automation, and conversational features into their applications and services. Azure OpenAI enhances productivity, fosters innovation, and boosts customer engagement, giving businesses a competitive advantage in today's data-driven landscape.

This introductory guide will showcase how to utilize Azure OpenAI with AzureML Prompt Flow, AzureML Notebooks, Snowflake, Azure SQLDB and the Snowflake/AzureSQL + AzureML Connector to swiftly generate results.

# Use Case
In this specific use case, you will utilize transaction history data from a large retail establishment and leverage the capabilities of Azure Open AI to generate three recommended next items that can be effectively marketed to the customer. Building Next Best Offer (NBO) applications often requires significant time and effort, but by utilizing Azure Openai, Prompt Flow and Azure SQLDB/Snowflake, you can expedite the setup process and complete it within hours.

Furthermore, the data incorporates demographic information, specifically the median age of the customer's zip code. This information has been directly sourced from [AGS - Sociodemographics](https://appliedgeographic.com/?_fsi=kZtuDsRp) via the Snowflake Marketplace.

Requirements:
- Familiarity with Snowflake and Azure SQL DB with an active active Snowflake account. You can create a 30-days free trial account.
- Familiarity with [Azure](https://azure.microsoft.com/en-us/get-started/azure-portal) and an active Azure account with an [AzureML workspace](https://learn.microsoft.com/en-us/azure/machine-learning/concept-workspace?view=azureml-api-2)
- Experience with [Python](https://www.python.org/about/gettingstarted/). Use the Python version 3.8 for this quickstart demo.

# Contents
1. Set up an Azure SQL database within your Azure Subscription.
2. Configure the Snowflake Environment.
3. Set up an AzureML Workspace.
4. Register and import data from both Azure SQL DB and Snowflake into AzureML.
5. Deploy the [Azure Open AI model](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/create-resource?pivots=web-portal).
6. Create a [Prompt Flow](https://learn.microsoft.com/en-us/azure/machine-learning/prompt-flow/overview-what-is-prompt-flow?view=azureml-api-2).
7. Utilize the Python scripts in a notebook to coordinate inference.


# Download and Install the ODBC driver for SQL Packages on your Azure ML compute terminal.
You can download the ODBC Driver 17 for SQL Server from the official Microsoft website or using `wget` command directly in the terminal. Here's the command to download the driver packages:

`wget https://packages.microsoft.com/debian/9/prod/pool/main/m/msodbcsql17/msodbcsql17_17.9.1.1-1_amd64.deb`

Install the Driver:

once the packages is downloaded, you can install the `dpkg` command. Run the following command in the terminal:
`sudo dpkg -i msodbcsql17_17.9.1.1-1_amd64.deb`

Verify Installation:
`odbcinst -q -d`

Configure Connection parameters:
Update your connection parameters in your python script or notebook to use the newly intalled ODBC driver.

Restart Compute Instance (if necessary):
In some cases, you may need to restart your Azure MAchine Learning compute instance for the changes to effect. 
  




