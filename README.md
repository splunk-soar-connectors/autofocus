[comment]: # "Auto-generated SOAR connector documentation"
# AutoFocus

Publisher: Splunk Community  
Connector Version: 1\.1\.4  
Product Vendor: Palo Alto Networks  
Product Name: AutoFocus  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.10\.0\.40961  

This App supports hunting actions and report retrieval on Palo Alto Networks AutoFocus

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a AutoFocus asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**api\_key** |  required  | password | AutoFocus API Key

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validates connectivity to AutoFocus  
[hunt file](#action-hunt-file) - Hunt a file and retrieve a list of associated tags  
[hunt ip](#action-hunt-ip) - Hunt an IP and retrieve a list of associated tags  
[hunt domain](#action-hunt-domain) - Hunt a domain and retrieve a list of associated tags  
[hunt url](#action-hunt-url) - Hunt a URL and retrieve a list of associated tags  
[get report](#action-get-report) - Get further details about an AutoFocus tag  

## action: 'test connectivity'
Validates connectivity to AutoFocus

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'hunt file'
Hunt a file and retrieve a list of associated tags

Type: **investigate**  
Read only: **True**

Use the <b>scope</b> parameter to specify the data set to hunt in\.<br>Valid values are\: <ul><li>My Samples<br>Hunt within your enterprise data</li><li>Public Samples<br>Hunt within AutoFocus public data set</li><li>All Samples<br>Use both data sets</li></ul>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**hash** |  required  | Hash \(MD5, SHA256, or SHA1\) of file | string |  `md5`  `sha256`  `sha1` 
**scope** |  optional  | Scope of search \(Default\: All Samples\) | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.hash | string |  `md5`  `sha256`  `sha1` 
action\_result\.parameter\.scope | string | 
action\_result\.data\.\*\.count | numeric | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.public\_tag\_name | string |  `autofocus tag` 
action\_result\.data\.\*\.tag\_name | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.total\_tags\_matched | numeric | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'hunt ip'
Hunt an IP and retrieve a list of associated tags

Type: **investigate**  
Read only: **True**

Use the <b>scope</b> parameter to specify the data set to hunt in\.<br>Valid values are\: <ul><li>My Samples<br>Hunt within your enterprise data</li><li>Public Samples<br>Hunt within AutoFocus public data set</li><li>All Samples<br>Use both data sets</li></ul>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP Address | string |  `ip` 
**scope** |  optional  | Scope of search \(Default\: All Samples\) | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.parameter\.scope | string | 
action\_result\.data\.\*\.count | numeric | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.public\_tag\_name | string |  `autofocus tag` 
action\_result\.data\.\*\.tag\_name | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.total\_tags\_matched | numeric | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'hunt domain'
Hunt a domain and retrieve a list of associated tags

Type: **investigate**  
Read only: **True**

Use the <b>scope</b> parameter to specify the data set to hunt in\.<br>Valid values are\: <ul><li>My Samples<br>Hunt within your enterprise data</li><li>Public Samples<br>Hunt within AutoFocus public data set</li><li>All Samples<br>Use both data sets</li></ul>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** |  required  | Domain | string |  `domain` 
**scope** |  optional  | Scope of search \(Default\: All Samples\) | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.domain | string |  `domain` 
action\_result\.parameter\.scope | string | 
action\_result\.data\.\*\.count | numeric | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.public\_tag\_name | string |  `autofocus tag` 
action\_result\.data\.\*\.tag\_name | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.total\_tags\_matched | numeric | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'hunt url'
Hunt a URL and retrieve a list of associated tags

Type: **investigate**  
Read only: **True**

Use the <b>scope</b> parameter to specify the data set to hunt in\.<br>Valid values are\: <ul><li>My Samples<br>Hunt within your enterprise data</li><li>Public Samples<br>Hunt within AutoFocus public data set</li><li>All Samples<br>Use both data sets</li></ul>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL | string |  `url` 
**scope** |  optional  | Scope of search \(Default\: All Samples\) | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.scope | string | 
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.count | numeric | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.public\_tag\_name | string |  `autofocus tag` 
action\_result\.data\.\*\.tag\_name | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.total\_tags\_matched | numeric | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get report'
Get further details about an AutoFocus tag

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**tag** |  required  | AutoFocus tag | string |  `autofocus tag` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.tag | string |  `autofocus tag` 
action\_result\.data\.\*\.bucket\_info\.daily\_bucket\_start | string | 
action\_result\.data\.\*\.bucket\_info\.daily\_points | numeric | 
action\_result\.data\.\*\.bucket\_info\.daily\_points\_remaining | numeric | 
action\_result\.data\.\*\.bucket\_info\.minute\_bucket\_start | string | 
action\_result\.data\.\*\.bucket\_info\.minute\_points | numeric | 
action\_result\.data\.\*\.bucket\_info\.minute\_points\_remaining | numeric | 
action\_result\.data\.\*\.tag\.comments\.\*\.comment | string | 
action\_result\.data\.\*\.tag\.comments\.\*\.comment\_type | string | 
action\_result\.data\.\*\.tag\.comments\.\*\.customer | string | 
action\_result\.data\.\*\.tag\.comments\.\*\.customer\_industry | string | 
action\_result\.data\.\*\.tag\.comments\.\*\.email | string | 
action\_result\.data\.\*\.tag\.comments\.\*\.first\_name | string | 
action\_result\.data\.\*\.tag\.comments\.\*\.last\_name | string | 
action\_result\.data\.\*\.tag\.comments\.\*\.submit\_time | string | 
action\_result\.data\.\*\.tag\.comments\.\*\.support\_id | numeric | 
action\_result\.data\.\*\.tag\.comments\.\*\.tag\_comment\_id | numeric | 
action\_result\.data\.\*\.tag\.comments\.\*\.tag\_report\_status\_id | numeric | 
action\_result\.data\.\*\.tag\.comments\.\*\.user\_id | numeric | 
action\_result\.data\.\*\.tag\.comments\.\*\.visibility | numeric | 
action\_result\.data\.\*\.tag\.count | numeric | 
action\_result\.data\.\*\.tag\.customer\_name | string | 
action\_result\.data\.\*\.tag\.description | string | 
action\_result\.data\.\*\.tag\.lasthit | string | 
action\_result\.data\.\*\.tag\.public\_tag\_name | string | 
action\_result\.data\.\*\.tag\.refs | string | 
action\_result\.data\.\*\.tag\.reported | boolean | 
action\_result\.data\.\*\.tag\.tag\_class | string | 
action\_result\.data\.\*\.tag\.tag\_class\_id | numeric | 
action\_result\.data\.\*\.tag\.tag\_definition\_scope | string | 
action\_result\.data\.\*\.tag\.tag\_definition\_scope\_id | numeric | 
action\_result\.data\.\*\.tag\.tag\_definition\_status | string | 
action\_result\.data\.\*\.tag\.tag\_definition\_status\_id | numeric | 
action\_result\.data\.\*\.tag\.tag\_name | string | 
action\_result\.data\.\*\.tag\_searches\.\*\.count | numeric | 
action\_result\.data\.\*\.tag\_searches\.\*\.lasthit | string | 
action\_result\.data\.\*\.tag\_searches\.\*\.search\_name | string | 
action\_result\.data\.\*\.tag\_searches\.\*\.tag\_definition\_search\_status | string | 
action\_result\.data\.\*\.tag\_searches\.\*\.tag\_definition\_search\_status\_id | numeric | 
action\_result\.data\.\*\.tag\_searches\.\*\.ui\_search\_definition | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 