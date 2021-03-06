# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0_amazon_msk] - 2020-11-24
### Added
- Pattern for a standalone Amazon MSK cluster. This template will create a cluster following best practices, such as sending broker logs to Amazon CloudWatch Logs; encryption at rest; encryption in transit among the broker nodes; and open monitoring with Prometheus enabled. It'll also include an Amazon EC2 instance that contains the Apache Kafka client libraries required to communicate with the cluster.
- Pattern for Amazon MSK and AWS Lambda, which can be used when you want to build a serverless application that consumes data from Apache Kafka topics. The default function is a Node.js application that logs the received messages, but it can be customized to your business needs.
- Pattern for Amazon MSK, AWS Lambda, and Amazon Kinesis Data Firehose. This option is intended for use cases when you need to backup messages from an Apache Kafka topic in Amazon MSK (for instance, to replay them). The data will be stored in Amazon S3, and can be analyzed with tools such as Amazon Athena and Amazon S3 Select.

### Changed
- Updated AWS CDK and AWS Solutions Constructs to version 1.74.0

## [1.2.0] - 2020-10-29
### Added
- Pattern for Amazon Kinesis Data Streams, Amazon Kinesis Data Firehose, and Amazon S3, which can be used when you want a simple way to back up incoming streaming data. Kinesis Data Firehose automatically takes care of compression and encryption, minimizing the amount of storage used at the destination and increasing security.
- Pattern for Amazon Kinesis Data Streams, Amazon Kinesis Data Analytics, and Amazon API Gateway, which can be used when you have a streaming application that needs to (asynchronously) invoke an external endpoint (for instance, to filter or enrich events). The interaction with the external system is made via the [Asynchronous I/O API of Apache Flink](https://ci.apache.org/projects/flink/flink-docs-stable/dev/stream/operators/asyncio.html).

### Changed
- The CloudWatch dashboard created for each pattern now includes CloudWatch alarms as widgets. Previously, to see the status of each alarm, you'd have to go to the Alarms page of the CloudWatch console.
- The Kinesis Analytics application CDK construct has been refactored, and it now accepts [runtime properties](https://docs.aws.amazon.com/kinesisanalytics/latest/java/how-properties.html) as parameters. Previously, the construct always expected to read from a Kinesis Data Stream and write to an S3 bucket, but now it can be used for more use cases.

### Fixed
- Resolved serialization issue with anonymous metrics

## [1.1.0] - 2020-09-17
### Changed
- Amazon Kinesis Data Analytics and AWS Lambda roles to use inline policies
- Demo application artifact names not to include version
- API Gateway and AWS Lambda pattern to use [AWS Solutions Constructs](https://aws.amazon.com/solutions/constructs/)

## [1.0.0] - 2020-08-31
### Added
- Pattern for Amazon API Gateway, Amazon Kinesis Data Streams, and AWS Lambda
- Pattern for Kinesis Producer Library, Amazon Kinesis Data Streams, and Amazon Kinesis Data Analytics
