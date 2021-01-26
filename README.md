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
Property Id: prp_605086
Contract Id: ctr_C-1IE2OHM
Group Id: grp_163363
Active Staging Version: 96
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

## Activate the config on Staging
```
>>>myProperty.activateStaging(18,"testing activation",["apadmana@akamai.com"])
True
```

## Activate the config on Production
```
>>>myProperty.activateProduction(18,"testing activation",["apadmana@akamai.com"])
True
```
## Get the version Active on Staging
```
>>>myProperty.getStagingVersion()
20
```

## Get the version Active on Production
```
>>>myProperty.getProductionVersion()
18
```

## Get the HostNames Present in the Config
```
>>>myProperty.getHostnames(12)
['achuth-lab.edgesuite-staging.net', 'achuth-lab.edgesuite.net']
```

## Get the Available Behaviours  in the Config
```
>>>myProperty.getAvailableFeatures(12)
['advanced', 'akamaizer', 'akamaizerTag', 'allHttpInCacheHierarchy', 'allowCloudletsOrigins', 'allowDelete', 'allowOptions', 'allowPatch', 'allowPost', 'allowPut', 'allowTransferEncoding', 'apiPrioritization', 'autoDomainValidation', 'baseDirectory', 'breakConnection', 'brotli', 'cacheError', 'cacheId', 'cacheKeyIgnoreCase', 'cacheKeyQueryParams', 'cacheKeyRewrite', 'cachePost', 'cacheRedirect', 'cacheTagVisible', 'caching', 'centralAuthorization', 'chaseRedirects', 'cloudInterconnects', 'constructResponse', 'corsSupport', 'cpCode', 'customBehavior', 'datastream', 'denyAccess', 'deviceCharacteristicCacheId', 'deviceCharacteristicHeader', 'dnsAsyncRefresh', 'dnsPrefresh', 'downstreamCache', 'edgeConnect', 'edgeImageConversion', 'edgeOriginAuthorization', 'edgeRedirector', 'edgeScape', 'edgeSideIncludes', 'enhancedAkamaiProtocol', 'failAction', 'failoverBotManagerFeatureCompatibility', 'firstPartyMarketing', 'forwardRewrite', 'globalRequestNumber', 'graphqlCaching', 'gzipResponse', 'healthDetection', 'http2', 'httpStrictTransportSecurity', 'imOverride', 'imageManager', 'instant', 'largeFileOptimization', 'mPulse', 'modifyIncomingRequestHeader', 'modifyIncomingResponseHeader', 'modifyOutgoingRequestHeader', 'modifyOutgoingResponseHeader', 'origin', 'originCharacteristics', 'persistentClientConnection', 'persistentConnection', 'personallyIdentifiableInformation', 'prefetch', 'prefetchable', 'prefreshCache', 'readTimeout', 'realUserMonitoring', 'redirect', 'redirectplus', 'refererChecking', 'removeQueryParameter', 'removeVary', 'report', 'requestControl', 'responseCode', 'responseCookie', 'returnCacheStatus', 'rewriteUrl', 'rumCustom', 'savePostDcaProcessing', 'scheduleInvalidation', 'setVariable', 'simulateErrorCode', 'siteShield', 'sureRoute', 'tcpOptimization', 'tieredDistribution', 'timeout', 'validateEntityTag', 'verifyTokenAuthorization', 'visitorPrioritization', 'watermarkUrl', 'webApplicationFirewall', 'webdav']
```
## Get the Used Behaviours  in the Config
```
>>>myProperty.getUsedBehaviors(12)
['origin', 'cpCode', 'caching', 'tieredDistribution', 'prefetch', 'allowPost', 'report', 'mPulse', 'gzipResponse', 'prefetchable', 'downstreamCache', 'removeVary', 'allowTransferEncoding', 'http2', 'deviceCharacteristicCacheId', 'deviceCharacteristicHeader', 'cacheKeyQueryParams', 'edgeRedirector', 'advanced', 'edgeSideIncludes', 'rewriteUrl', 'setVariable', 'forwardRewrite', 'modifyIncomingResponseHeader', 'cacheTagVisible', 'cacheId']
```
