# CDP Data Lake creation for AWS
<div align="center">
<img src="https://github.com/paulvid/emr_to_cdp/raw/master/data/cloudera_logo_darkorange.png" width="820" height="100" align="middle">
</div>

# Overview

This set of scripts automates the creation of all minimal pre-requisites to setup a CDP AWS datalake, including:
* Syncing proper roles to existing environment
* Set of minimal AWS policies
* Set of minimal AWS roles
* CDP environment creation

# Setup

## Pre-requisites

* CDP environment created (see [Tutorial](https://github.com/paulvid/cdp_create_env_aws/))
* AWS cli: Configure AWS cli with your credentials and region
* CDP cli: Configure CDP cli with your credentials and region


## Setup


### 1. Clone this repository
```
git clone https://github.com/paulvid/cdp_create_dl_aws.git
```

### 2. Run the following scripts in order


Create roles and mapping in your existing environment:
```
cdp_create_group_iam.sh <base_dir> <prefix> 
```

Create datalake:
```
cdp_create_datalake.sh <base_dir> <prefix> 
```

### 3. Verify periodically until datalake status is RUNNING

```
cdp_describe_dl.sh <prefix> 
```

### 4. Sync free IPA users

```
cdp_sync_users.sh <base_dir> <prefix> 
```


# Authors

**Paul Vidal** - *Initial work* - [LinkedIn](https://www.linkedin.com/in/paulvid/)
