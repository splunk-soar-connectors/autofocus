[comment]: # "Auto-generated SOAR connector documentation"
# AutoFocus

Publisher: Splunk Community  
Connector Version: 1.1.6  
Product Vendor: Palo Alto Networks  
Product Name: AutoFocus  
Product Version Supported (regex): ".\*"  
Minimum Product Version: 4.10.0.40961  

This App supports hunting actions and report retrieval on Palo Alto Networks AutoFocus

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a AutoFocus asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**api_key** |  required  | password | AutoFocus API Key

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

Use the <b>scope</b> parameter to specify the data set to hunt in.<br>Valid values are: <ul><li>My Samples<br>Hunt within your enterprise data</li><li>Public Samples<br>Hunt within AutoFocus public data set</li><li>All Samples<br>Use both data sets</li></ul>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**hash** |  required  | Hash (MD5, SHA256, or SHA1) of file | string |  `md5`  `sha256`  `sha1` 
**scope** |  optional  | Scope of search (Default: All Samples) | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.hash | string |  `md5`  `sha256`  `sha1`  |  
action_result.parameter.scope | string |  |  
action_result.data.\*.count | numeric |  |  
action_result.data.\*.description | string |  |  
action_result.data.\*.public_tag_name | string |  `autofocus tag`  |  
action_result.data.\*.tag_name | string |  |  
action_result.status | string |  |   success  failed 
action_result.message | string |  |  
action_result.summary.total_tags_matched | numeric |  |  
summary.total_objects | numeric |  |  
summary.total_objects_successful | numeric |  |    

## action: 'hunt ip'
Hunt an IP and retrieve a list of associated tags

Type: **investigate**  
Read only: **True**

Use the <b>scope</b> parameter to specify the data set to hunt in.<br>Valid values are: <ul><li>My Samples<br>Hunt within your enterprise data</li><li>Public Samples<br>Hunt within AutoFocus public data set</li><li>All Samples<br>Use both data sets</li></ul>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP Address | string |  `ip` 
**scope** |  optional  | Scope of search (Default: All Samples) | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.ip | string |  `ip`  |  
action_result.parameter.scope | string |  |  
action_result.data.\*.count | numeric |  |  
action_result.data.\*.description | string |  |  
action_result.data.\*.public_tag_name | string |  `autofocus tag`  |  
action_result.data.\*.tag_name | string |  |  
action_result.status | string |  |   success  failed 
action_result.message | string |  |  
action_result.summary.total_tags_matched | numeric |  |  
summary.total_objects | numeric |  |  
summary.total_objects_successful | numeric |  |    

## action: 'hunt domain'
Hunt a domain and retrieve a list of associated tags

Type: **investigate**  
Read only: **True**

Use the <b>scope</b> parameter to specify the data set to hunt in.<br>Valid values are: <ul><li>My Samples<br>Hunt within your enterprise data</li><li>Public Samples<br>Hunt within AutoFocus public data set</li><li>All Samples<br>Use both data sets</li></ul>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** |  required  | Domain | string |  `domain` 
**scope** |  optional  | Scope of search (Default: All Samples) | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.domain | string |  `domain`  |  
action_result.parameter.scope | string |  |  
action_result.data.\*.count | numeric |  |  
action_result.data.\*.description | string |  |  
action_result.data.\*.public_tag_name | string |  `autofocus tag`  |  
action_result.data.\*.tag_name | string |  |  
action_result.status | string |  |   success  failed 
action_result.message | string |  |  
action_result.summary.total_tags_matched | numeric |  |  
summary.total_objects | numeric |  |  
summary.total_objects_successful | numeric |  |    

## action: 'hunt url'
Hunt a URL and retrieve a list of associated tags

Type: **investigate**  
Read only: **True**

Use the <b>scope</b> parameter to specify the data set to hunt in.<br>Valid values are: <ul><li>My Samples<br>Hunt within your enterprise data</li><li>Public Samples<br>Hunt within AutoFocus public data set</li><li>All Samples<br>Use both data sets</li></ul>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL | string |  `url` 
**scope** |  optional  | Scope of search (Default: All Samples) | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.scope | string |  |  
action_result.parameter.url | string |  `url`  |  
action_result.data.\*.count | numeric |  |  
action_result.data.\*.description | string |  |  
action_result.data.\*.public_tag_name | string |  `autofocus tag`  |  
action_result.data.\*.tag_name | string |  |  
action_result.status | string |  |   success  failed 
action_result.message | string |  |  
action_result.summary.total_tags_matched | numeric |  |  
summary.total_objects | numeric |  |  
summary.total_objects_successful | numeric |  |    

## action: 'get report'
Get further details about an AutoFocus tag

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**tag** |  required  | AutoFocus tag | string |  `autofocus tag` 

#### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.tag | string |  `autofocus tag`  |  
action_result.data.\*.bucket_info.daily_bucket_start | string |  |  
action_result.data.\*.bucket_info.daily_points | numeric |  |  
action_result.data.\*.bucket_info.daily_points_remaining | numeric |  |  
action_result.data.\*.bucket_info.minute_bucket_start | string |  |  
action_result.data.\*.bucket_info.minute_points | numeric |  |  
action_result.data.\*.bucket_info.minute_points_remaining | numeric |  |  
action_result.data.\*.tag.comments.\*.comment | string |  |  
action_result.data.\*.tag.comments.\*.comment_type | string |  |  
action_result.data.\*.tag.comments.\*.customer | string |  |  
action_result.data.\*.tag.comments.\*.customer_industry | string |  |  
action_result.data.\*.tag.comments.\*.email | string |  |  
action_result.data.\*.tag.comments.\*.first_name | string |  |  
action_result.data.\*.tag.comments.\*.last_name | string |  |  
action_result.data.\*.tag.comments.\*.submit_time | string |  |  
action_result.data.\*.tag.comments.\*.support_id | numeric |  |  
action_result.data.\*.tag.comments.\*.tag_comment_id | numeric |  |  
action_result.data.\*.tag.comments.\*.tag_report_status_id | numeric |  |  
action_result.data.\*.tag.comments.\*.user_id | numeric |  |  
action_result.data.\*.tag.comments.\*.visibility | numeric |  |  
action_result.data.\*.tag.count | numeric |  |  
action_result.data.\*.tag.customer_name | string |  |  
action_result.data.\*.tag.description | string |  |  
action_result.data.\*.tag.lasthit | string |  |  
action_result.data.\*.tag.public_tag_name | string |  |  
action_result.data.\*.tag.refs | string |  |  
action_result.data.\*.tag.reported | boolean |  |  
action_result.data.\*.tag.tag_class | string |  |  
action_result.data.\*.tag.tag_class_id | numeric |  |  
action_result.data.\*.tag.tag_definition_scope | string |  |  
action_result.data.\*.tag.tag_definition_scope_id | numeric |  |  
action_result.data.\*.tag.tag_definition_status | string |  |  
action_result.data.\*.tag.tag_definition_status_id | numeric |  |  
action_result.data.\*.tag.tag_name | string |  |  
action_result.data.\*.tag_searches.\*.count | numeric |  |  
action_result.data.\*.tag_searches.\*.lasthit | string |  |  
action_result.data.\*.tag_searches.\*.search_name | string |  |  
action_result.data.\*.tag_searches.\*.tag_definition_search_status | string |  |  
action_result.data.\*.tag_searches.\*.tag_definition_search_status_id | numeric |  |  
action_result.data.\*.tag_searches.\*.ui_search_definition | string |  |  
action_result.status | string |  |   success  failed 
action_result.message | string |  |  
action_result.summary | string |  |  
summary.total_objects | numeric |  |  
summary.total_objects_successful | numeric |  |  