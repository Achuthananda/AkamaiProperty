# A Python Class for Akamai Property
An Object oriented implementation of Akamai Property.
The advantage of Akamai Property class is application developers need not know about the PAPI calls and their usage. Application developers can just focus on getting their work done on Property Manager configs programmatically using the objects of AkamaiProperty.


### Credentials
In order to use this configuration, you need to:
* Set up your credential files as described in the [authorization](https://developer.akamai.com/introduction/Prov_Creds.html) and [credentials](https://developer.akamai.com/introduction/Conf_Client.html) sections of the getting started guide on developer.akamai.com.  
* When working through this process you need to give grants for the property manager API and the User Admin API (if you will want to move properties).  The section in your configuration file should be called 'papi'.

## Overview
The advantage of Akamai Property class is application developers need not know about the PAPI calls and their usage. Application developers can just focus on getting their work done on Property Manager configs programmatically using the objects of AkamaiProperty.


## Install Dependencies If you are using source code.
```
$ pip install -r requirements.txt
```

### Install pip package available
```
$ pip install akamaiproperty
```

## Instantiate the object.
```
>>> from akamaiproperty import AkamaiProperty
>>> myProperty = AkamaiProperty("/Users/apadmana/.edgerc","test_bulkseach_update_1","<accountSwitchKey>")
>>> myProperty = AkamaiProperty("/Users/apadmana/.edgerc","test_bulkseach_update_1")
```

## Print Basic Information
```
>>> myProperty.printPropertyInfo()
Property Name: test_bulkseach_update_1
Contract Id: ctr_C-1IE2OHM
Group Id: grp_163363
Active Staging Version: 18
Active Production Version: 18
```
## Create a new version
```
>>> myProperty.createVersion(18)
'78'
```

## Get rule Tree
```
>>>myProperty.getRuleTree(18)
{'accountId': 'act_B-C-1IE2OH8', 'contractId': 'ctr_C-1IE2OHM', 'groupId': 'grp_163363', 'propertyId': 'prp_605086', 'propertyName': 'test_bulkseach_update_1', 'propertyVersion': 18, 'etag': 'd0d28a6b71e665144955f7f7e1ff214933d119d7', 'rules':.....}
```

## Activate the config
```
>>>myProperty.activateStaging(18,"testing activation",["apadmana@akamai.com"])
True
```

## Class Definition
```
class AkamaiProperty():
    def __init__(self,edgercLocation, name, accountSwitchKey=None):
        self.name = name
        self.contractId = ''
        self.groupId = ''
        self.propertyId = ''
        self.stagingVersion = 0
        self.productionVersion = 0
        self.accountSwitchKey = ''

    def printPropertyInfo(self)
    def getStagingVersion(self)
    def getProductionVersion(self)
    def getRuleTree(self,version)
    def updateRuleTree(self,version,jsondata)
    def createVersion(self,baseVersion)
    def activateStaging(self,version,notes,email_list)
    def activateProduction(self,version,notes,email_list,peer_review_email,customer_email)
```
