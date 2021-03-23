# AWS CloudWatch Logs Terraform Module #

This Terraform module deploys an AWS CloudWatch Log Stream and Group.

## Requirements

| Name      | Version |
| --------- | ------- |
| terraform | >= 0.12 |

## Providers

| Name | Version |
| ---- | ------- |
| aws  | n/a     |

## Inputs

| Name                                             | Description                                                        | Type   | Default | Required |
| ------------------------------------------------ | ------------------------------------------------------------------ | ------ | ------- | :------: |
| logs\_path                                       | Path of the logs in CloudWatch                   | `string` | n/a     |   yes    |
| log\_group\_retention\_in\_days                  | (Optional) Specifies the number of days you want to retain log events in the specified log group. Default to 30 days     | `number`  | `30`     |   no    |
| log\_group\_kms\_key\_id                         | The ARN of the KMS Key to use when encrypting log data. Please note, after the AWS KMS CMK is disassociated from the log group, AWS CloudWatch Logs stops encrypting newly ingested data for the log group. All previously ingested data remains encrypted, and AWS CloudWatch Logs requires permissions for the CMK whenever the encrypted data is requested. | `string` | `""`     |   no    |


## Outputs

| Name                               | Description                                                                                            |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------ |
| logs\_path                         | Path of the logs in CloudWatch                                                                         |
| log\_group\_name                   | The name of the log group.                                                                             |
| log\_group\_retention\_in\_days    | Specifies the number of days log events are retained.                                                  |
| log\_group\_arn                    | The Amazon Resource Name (ARN) specifying the log group.                                               |
| log\_stream\_name                  | The name of the log stream.                                                                            |
| log\_stream\_log\_group\_name      | The name of the log group under which the log stream was created.                                      |
| log\_stream\_arn                   | The Amazon Resource Name (ARN) specifying the log stream.                                              |
