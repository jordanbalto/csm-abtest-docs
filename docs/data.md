# Data

## Sharing

### File Structure
When a new data sharing cadence is established for a customer conducting an AB test or pilot, 
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
1062843|med\_advantage|6/14/21|WTed88aae6b4cfe5d50b3b859810f92f3d|FALSE|108|[60, 80)|FALSE|FALSE| | |experiment
1098622|med\_advantage|6/25/21|WT0dab9e12bc77f3fbf6c0eb31fddbc95f|FALSE|245|[40, 60)|FALSE|FALSE| | |experiment
1084931|life|6/25/21|WTa091794278df3b07c7d4a22507ca7f29|FALSE|40|[0, 20)|FALSE|FALSE| | |experiment
1117808|med\_advantage|6/28/21|WT004cc1db36cf8a24c3f7d78fb9862002|FALSE|297|[40, 60)|FALSE|FALSE| | |control
1084877|life|6/28/21|WT33b6e4cf14b9bb746a68a306c6ffbdde|FALSE|61|[0, 20)|FALSE|FALSE| | |experiment
1085334|med\_advantage|6/28/21|WT5fd43bf6-5e6a-4de9-8244-809224a8214a|TRUE|536| |FALSE|FALSE| | |experiment
1084461|med\_advantage|6/29/21|WTbf85c17c03274fef98d8906833429fb5|FALSE|938|[20, 40)|FALSE|FALSE| | |experiment
1008973|life|6/30/21|WTa1ee6823c851f53d6e96115e45cbdb46|FALSE|721|[40, 60)|FALSE|FALSE| | |control

### Agent-time level
**CallDate**|**DateGroup**|**VendorCampaignName**|**Agent**|**BaltoGroup**|**AgentLevel**|**DialAttempt**|**GrossConnections**|**HumanContacts**|**Total\_Att\_Transfers**|**UniqueTransferAttempts**|**UniqueConnectedTransfers**|**UniqueTransferSuccess**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
2021-09-01|Pre-Test|Allied - Campaign - SQS Lead Screening|allied\_aogbeh|Test|Specialty|1|1|1|0|0|0|0
2021-09-01|Pre-Test|Allied - Campaign - SQS Lead Screening|allied\_aogbeh|Test|Specialty|2|1|1|0|0|0|0
2021-09-01|Pre-Test|Allied - Life Standard|allied\_aogbeh|Test|Specialty|2|1|1|0|0|0|0
2021-09-01|Pre-Test|Allied - Life Standard|allied\_aogbeh|Test|Specialty|3+|2|1|0|0|0|0
2021-09-01|Pre-Test|Allied - Medicare Standard|allied\_aogbeh|Test|Specialty|1|87|56|5|5|5|5
2021-09-01|Pre-Test|Allied - Medicare Standard|allied\_aogbeh|Test|Specialty|2|7|3|0|0|0|0
2021-09-01|Pre-Test|Allied - Medicare Standard|allied\_aogbeh|Test|Specialty|3+|163|60|4|4|3|2
2021-09-01|Pre-Test|Allied - Medicare Standard - Double Dial|allied\_aogbeh|Test|Specialty|1|11|5|2|2|1|1
2021-09-01|Pre-Test|Allied - Medicare Standard - Double Dial|allied\_aogbeh|Test|Specialty|2|27|11|3|3|3|2