# Data

## Sharing

### File Structure
When a new data sharing cadence is established for a customer conducting an A/B test or pilot, 
the CSM will be tasked with delivering the raw data to a hierarchical directory structure in the following format:

```
ab-test-customer-data/
└── CUSTOMER/
    └── DATA_FOLDER/
```

`ab-test-customer-data` is a directory located on Google Drive in `Customer Success Team Drive`. 
`CUSTOMER` should be informative to the specific customer the pilot is being conducted for, and `DATA_FOLDER` 
specific to a single pilot. An example of this file structure can be found [here](https://drive.google.com/drive/folders/16CR_IrDc8cZiTcfSN955sWDA2lFwTORd?usp=sharing).
When naming these folders, please avoid using capitalization, special characters and spaces as this can introduce unnecessary complications. 
For example, `bradley_lead_group` or `blg` are acceptable directory names, while `Bradley Lead Group` is not.
If there are security requirements from a specific client that require FTP or something similar, DS will attempt to accommodate those needs.

## Examples
Typically, customers share data in one of two formats--call-level data, or agent-time level data. 
Like the name implies, call-level data are records where each observation (or row) is a single call. To use call-level data during a test, DS
at a bare minimum must know whether the call as successful, whether the call was made using Balto, and the date/time of the call.

Agent-level data are records where each observation represents a single agent-time (e.g. day or week) combination. To use this type of data for a test
the bare minimum DS needs are who the agent is, whether they are a Balto user, the time unit of observation, and the KPI value for each agent-time row. Below are example data sets for each general type of data.

### Call-level
**user\_id**|**line\_of\_insurance**|**call\_date\_pst**|**contact\_id**|**is\_outbound**|**call\_duration\_seconds**|**inbound\_call\_ltv\_bucket**|**is\_transfer**|**policy\_sale**|**monthly\_premium**|**ltv**|**user\_type**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
1234567|med\_advantage|6/14/21|XXX|FALSE|108|[60, 80)|FALSE|FALSE| | |experiment
2222222|med\_advantage|6/25/21|XXX|FALSE|245|[40, 60)|FALSE|FALSE| | |experiment
3333333|life|6/25/21|XXX|FALSE|40|[0, 20)|FALSE|FALSE| | |experiment
4444444|med\_advantage|6/28/21|XXX|FALSE|297|[40, 60)|FALSE|FALSE| | |control
5555555|life|6/28/21|XXX|FALSE|61|[0, 20)|FALSE|FALSE| | |experiment
6666666|med\_advantage|6/28/21|XXX|TRUE|536| |FALSE|FALSE| | |experiment
7777777|med\_advantage|6/29/21|XXX|FALSE|938|[20, 40)|FALSE|FALSE| | |experiment
8888888|life|6/30/21|XXX|FALSE|721|[40, 60)|FALSE|FALSE| | |control

### Agent-time level
**CallDate**|**DateGroup**|**VendorCampaignName**|**Agent**|**BaltoGroup**|**AgentLevel**|**DialAttempt**|**GrossConnections**|**HumanContacts**|**Total\_Att\_Transfers**|**UniqueTransferAttempts**|**UniqueConnectedTransfers**|**UniqueTransferSuccess**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
2021-09-01|Pre-Test|Allied - Campaign - SQS Lead Screening|allied\_tyler|Test|Specialty|1|1|1|0|0|0|0
2021-09-01|Pre-Test|Allied - Campaign - SQS Lead Screening|allied\_tyler|Test|Specialty|2|1|1|0|0|0|0
2021-09-01|Pre-Test|Allied - Life Standard|allied\_tyler|Test|Specialty|2|1|1|0|0|0|0
2021-09-01|Pre-Test|Allied - Life Standard|allied\_tyler|Test|Specialty|3+|2|1|0|0|0|0
2021-09-01|Pre-Test|Allied - Medicare Standard|allied\_tyler|Test|Specialty|1|87|56|5|5|5|5
2021-09-01|Pre-Test|Allied - Medicare Standard|allied\_tyler|Test|Specialty|2|7|3|0|0|0|0
2021-09-01|Pre-Test|Allied - Medicare Standard|allied\_tyler|Test|Specialty|3+|163|60|4|4|3|2
2021-09-01|Pre-Test|Allied - Medicare Standard - Double Dial|allied\_tyler|Test|Specialty|1|11|5|2|2|1|1
2021-09-01|Pre-Test|Allied - Medicare Standard - Double Dial|allied\_tyler|Test|Specialty|2|27|11|3|3|3|2