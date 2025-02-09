<!-- DO NOT EDIT: this file is automatically generated using scw-doc-gen -->
# Documentation for `scw mnq`
Messaging and Queuing NATS API.
  
- [MnQ NATS commands](#mnq-nats-commands)
  - [Create a NATS account](#create-a-nats-account)
  - [Create NATS credentials](#create-nats-credentials)
  - [Delete a NATS account](#delete-a-nats-account)
  - [Delete NATS credentials](#delete-nats-credentials)
  - [Get a NATS account](#get-a-nats-account)
  - [Get NATS credentials](#get-nats-credentials)
  - [List NATS accounts](#list-nats-accounts)
  - [List NATS credentials](#list-nats-credentials)
  - [Update the name of a NATS account](#update-the-name-of-a-nats-account)
- [MnQ SNS commands](#mnq-sns-commands)
  - [Activate SNS](#activate-sns)
  - [Create SNS credentials](#create-sns-credentials)
  - [Deactivate SNS](#deactivate-sns)
  - [Delete SNS credentials](#delete-sns-credentials)
  - [Get SNS credentials](#get-sns-credentials)
  - [Get SNS info](#get-sns-info)
  - [List SNS credentials](#list-sns-credentials)
  - [Update SNS credentials](#update-sns-credentials)
- [MnQ SQS commands](#mnq-sqs-commands)
  - [Activate SQS](#activate-sqs)
  - [Create SQS credentials](#create-sqs-credentials)
  - [Deactivate SQS](#deactivate-sqs)
  - [Delete SQS credentials](#delete-sqs-credentials)
  - [Get SQS credentials](#get-sqs-credentials)
  - [Get SQS info](#get-sqs-info)
  - [List SQS credentials](#list-sqs-credentials)
  - [Update SQS credentials](#update-sqs-credentials)

  
## MnQ NATS commands

MnQ NATS commands.


### Create a NATS account

Create a NATS account associated with a Project.

**Usage:**

```
scw mnq nats create-account [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| name | Default: `<generated>` | NATS account name |
| project-id |  | Project ID to use. If none is passed the default project ID will be used |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Create NATS credentials

Create a set of credentials for a NATS account, specified by its NATS account ID.

**Usage:**

```
scw mnq nats create-credentials [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| nats-account-id | Required | NATS account containing the credentials |
| name | Default: `<generated>` | Name of the credentials |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Delete a NATS account

Delete a NATS account, specified by its NATS account ID. Note that deleting a NATS account is irreversible, and any credentials, streams, consumer and stored messages belonging to this NATS account will also be deleted.

**Usage:**

```
scw mnq nats delete-account <nats-account-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| nats-account-id | Required | ID of the NATS account to delete |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Delete NATS credentials

Delete a set of credentials, specified by their credentials ID. Deleting credentials is irreversible and cannot be undone. The credentials can no longer be used to access the NATS account, and active connections using this credentials will be closed.

**Usage:**

```
scw mnq nats delete-credentials <nats-credentials-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| nats-credentials-id | Required | ID of the credentials to delete |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Get a NATS account

Retrieve information about an existing NATS account identified by its NATS account ID. Its full details, including name and endpoint, are returned in the response.

**Usage:**

```
scw mnq nats get-account <nats-account-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| nats-account-id | Required | ID of the NATS account to get |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Get NATS credentials

Retrieve an existing set of credentials, identified by the `nats_credentials_id`. The credentials themselves are NOT returned, only their metadata (NATS account ID, credentials name, etc), are returned in the response.

**Usage:**

```
scw mnq nats get-credentials <nats-credentials-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| nats-credentials-id | Required | ID of the credentials to get |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### List NATS accounts

List all NATS accounts in the specified region, for a Scaleway Organization or Project. By default, the NATS accounts returned in the list are ordered by creation date in ascending order, though this can be modified via the `order_by` field.

**Usage:**

```
scw mnq nats list-accounts [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Include only NATS accounts in this Project |
| order-by | One of: `created_at_asc`, `created_at_desc`, `updated_at_asc`, `updated_at_desc`, `name_asc`, `name_desc` | Order in which to return results |
| region | Default: `fr-par`<br />One of: `fr-par`, `all` | Region to target. If none is passed will use default region from the config |



### List NATS credentials

List existing credentials in the specified NATS account. The response contains only the metadata for the credentials, not the credentials themselves, which are only returned after a **Create Credentials** call.

**Usage:**

```
scw mnq nats list-credentials [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| nats-account-id | Required | Include only credentials for this NATS account |
| order-by | One of: `created_at_asc`, `created_at_desc`, `updated_at_asc`, `updated_at_desc`, `name_asc`, `name_desc` | Order in which to return results |
| region | Default: `fr-par`<br />One of: `fr-par`, `all` | Region to target. If none is passed will use default region from the config |



### Update the name of a NATS account

Update the name of a NATS account, specified by its NATS account ID.

**Usage:**

```
scw mnq nats update-account <nats-account-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| nats-account-id | Required | ID of the NATS account to update |
| name |  | NATS account name |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



## MnQ SNS commands

MnQ SNS commands.


### Activate SNS

Activate SNS for the specified Project ID. SNS must be activated before any usage. Activating SNS does not trigger any billing, and you can deactivate at any time.

**Usage:**

```
scw mnq sns activate [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Project ID to use. If none is passed the default project ID will be used |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Create SNS credentials

Create a set of credentials for SNS, specified by a Project ID. Credentials give the bearer access to topics, and the level of permissions can be defined granularly.

**Usage:**

```
scw mnq sns create-credentials [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Project ID to use. If none is passed the default project ID will be used |
| name | Default: `<generated>` | Name of the credentials |
| permissions.can-publish |  | Defines whether the credentials bearer can publish messages to the service (publish to SNS topics) |
| permissions.can-receive |  | Defines whether the credentials bearer can receive messages from the service (configure subscriptions) |
| permissions.can-manage |  | Defines whether the credentials bearer can manage the associated SNS topics or subscriptions |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Deactivate SNS

Deactivate SNS for the specified Project ID.You must delete all topics and credentials before this call or you need to set the force_delete parameter.

**Usage:**

```
scw mnq sns deactivate [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Project ID to use. If none is passed the default project ID will be used |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Delete SNS credentials

Delete a set of SNS credentials, specified by their credentials ID. Deleting credentials is irreversible and cannot be undone. The credentials can then no longer be used to access SNS.

**Usage:**

```
scw mnq sns delete-credentials <sns-credentials-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| sns-credentials-id | Required | ID of the credentials to delete |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Get SNS credentials

Retrieve an existing set of credentials, identified by the `credentials_id`. The credentials themselves, as well as their metadata (name, project ID etc), are returned in the response.

**Usage:**

```
scw mnq sns get-credentials <sns-credentials-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| sns-credentials-id | Required | ID of the SNS credentials to get |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Get SNS info

Retrieve the SNS information of the specified Project ID. Informations include the activation status and the SNS API endpoint URL.

**Usage:**

```
scw mnq sns get-info [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Project ID to use. If none is passed the default project ID will be used |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### List SNS credentials

List existing SNS credentials in the specified region. The response contains only the metadata for the credentials, not the credentials themselves.

**Usage:**

```
scw mnq sns list-credentials [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Include only SNS credentials in this Project |
| order-by | One of: `created_at_asc`, `created_at_desc`, `updated_at_asc`, `updated_at_desc`, `name_asc`, `name_desc` | Order in which to return results |
| region | Default: `fr-par`<br />One of: `fr-par`, `all` | Region to target. If none is passed will use default region from the config |



### Update SNS credentials

Update a set of SNS credentials. You can update the credentials' name, or their permissions.

**Usage:**

```
scw mnq sns update-credentials <sns-credentials-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| sns-credentials-id | Required | ID of the SNS credentials to update |
| name |  | Name of the credentials |
| permissions.can-publish |  | Defines whether the credentials bearer can publish messages to the service (publish to SNS topics) |
| permissions.can-receive |  | Defines whether the credentials bearer can receive messages from the service (configure subscriptions) |
| permissions.can-manage |  | Defines whether the credentials bearer can manage the associated SNS topics or subscriptions |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



## MnQ SQS commands

MnQ SQS commands.


### Activate SQS

Activate SQS for the specified Project ID. SQS must be activated before any usage such as creating credentials and queues. Activating SQS does not trigger any billing, and you can deactivate at any time.

**Usage:**

```
scw mnq sqs activate [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Project ID to use. If none is passed the default project ID will be used |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Create SQS credentials

Create a set of credentials for SQS, specified by a Project ID. Credentials give the bearer access to queues, and the level of permissions can be defined granularly.

**Usage:**

```
scw mnq sqs create-credentials [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Project ID to use. If none is passed the default project ID will be used |
| name | Default: `<generated>` | Name of the credentials |
| permissions.can-publish |  | Defines whether the credentials bearer can publish messages to the service (send messages to SQS queues) |
| permissions.can-receive |  | Defines whether the credentials bearer can receive messages from SQS queues |
| permissions.can-manage |  | Defines whether the credentials bearer can manage the associated SQS queues |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Deactivate SQS

Deactivate SQS for the specified Project ID. You must delete all queues and credentials before this call or you need to set the force_delete parameter.

**Usage:**

```
scw mnq sqs deactivate [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Project ID to use. If none is passed the default project ID will be used |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Delete SQS credentials

Delete a set of SQS credentials, specified by their credentials ID. Deleting credentials is irreversible and cannot be undone. The credentials can then no longer be used to access SQS.

**Usage:**

```
scw mnq sqs delete-credentials <sqs-credentials-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| sqs-credentials-id | Required | ID of the credentials to delete |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Get SQS credentials

Retrieve an existing set of credentials, identified by the `credentials_id`. The credentials themselves, as well as their metadata (name, project ID etc), are returned in the response.

**Usage:**

```
scw mnq sqs get-credentials <sqs-credentials-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| sqs-credentials-id | Required | ID of the SQS credentials to get |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### Get SQS info

Retrieve the SQS information of the specified Project ID. Informations include the activation status and the SQS API endpoint URL.

**Usage:**

```
scw mnq sqs get-info [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Project ID to use. If none is passed the default project ID will be used |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



### List SQS credentials

List existing SQS credentials in the specified region. The response contains only the metadata for the credentials, not the credentials themselves.

**Usage:**

```
scw mnq sqs list-credentials [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| project-id |  | Include only SQS credentials in this Project |
| order-by | One of: `created_at_asc`, `created_at_desc`, `updated_at_asc`, `updated_at_desc`, `name_asc`, `name_desc` | Order in which to return results |
| region | Default: `fr-par`<br />One of: `fr-par`, `all` | Region to target. If none is passed will use default region from the config |



### Update SQS credentials

Update a set of SQS credentials. You can update the credentials' name, or their permissions.

**Usage:**

```
scw mnq sqs update-credentials <sqs-credentials-id ...> [arg=value ...]
```


**Args:**

| Name |   | Description |
|------|---|-------------|
| sqs-credentials-id | Required | ID of the SQS credentials to update |
| name |  | Name of the credentials |
| permissions.can-publish |  | Defines whether the credentials bearer can publish messages to the service (send messages to SQS queues) |
| permissions.can-receive |  | Defines whether the credentials bearer can receive messages from SQS queues |
| permissions.can-manage |  | Defines whether the credentials bearer can manage the associated SQS queues |
| region | Default: `fr-par`<br />One of: `fr-par` | Region to target. If none is passed will use default region from the config |



