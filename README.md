[![Build Status](https://travis-ci.org/cfn-modules/ecs-cluster.svg?branch=master)](https://travis-ci.org/cfn-modules/ecs-cluster)
[![NPM version](https://img.shields.io/npm/v/@cfn-modules/ecs-cluster.svg)](https://www.npmjs.com/package/@cfn-modules/ecs-cluster)

# cfn-modules: ECS cluster EC2

ECS cluster EC2.

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/ecs-cluster
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  Cluster:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      TemplateURL: './node_modules/@cfn-modules/ecs-cluster/module.yml'

```

## Examples

none

## Related modules

* [ecs-service](https://github.com/cfn-modules/ecs-service)

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>VpcModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/vpc">vpc module</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>AlbModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/alb">alb module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AlertingModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/alerting">alerting module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>BastionModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/search?q=keywords:cfn-modules:Bastion">module implementing Bastion</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>KeyName</td>
      <td>Key name of the Linux user ec2-user to establish a SSH connection to the EC2 instance</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>IAMUserSSHAccess</td>
      <td>Synchronize public keys of IAM users to enable personalized SSH access (https://github.com/widdix/aws-ec2-ssh)?</td>
      <td>false</td>
      <td>no</td>
      <td>[true, false]</td>
    </tr>
    <tr>
      <td>SystemsManagerAccess</td>
      <td>Enable AWS Systems Manager agent and authorization</td>
      <td>true</td>
      <td>no</td>
      <td>[true, false]</td>
    </tr>
    <tr>
      <td>InstanceType</td>
      <td>The instance type for the EC2 instance</td>
      <td>t2.micro</td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>InstanceName</td>
      <td>The name for the EC2 instance</td>
      <td>auto generated value</td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SubnetReach</td>
      <td>Subnet reach</td>
      <td>Public</td>
      <td>no</td>
      <td>[Public, Private]</td>
    </tr>
    <tr>
      <td>LogsRetentionInDays</td>
      <td>Specifies the number of days you want to retain log events</td>
      <td>14</td>
      <td>no</td>
      <td>[1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, 3653]</td>
    </tr>
    <tr>
      <td>UserData</td>
      <td>Bash script executed on first instance launch</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>IngressTcpPort1</td>
      <td>Port allowing ingress TCP traffic</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>IngressTcpPort2</td>
      <td>Port allowing ingress TCP traffic</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>IngressTcpPort3</td>
      <td>Port allowing ingress TCP traffic</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ClientSgModule1</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/client-sg">client-sg module</a> module to mark traffic from EC2 instance</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ClientSgModule2</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/client-sg">client-sg module</a> module to mark traffic from EC2 instance</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ClientSgModule3</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/client-sg">client-sg module</a> module to mark traffic from EC2 instance</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>FileSystemModule1</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/efs-file-system">efs-file-system module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>FileSystemModule2</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/efs-file-system">efs-file-system module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>FileSystemModule3</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/efs-file-system">efs-file-system module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>MinSize</td>
      <td>The minimum size of the Auto Scaling group</td>
      <td>2</td>
      <td>no</td>
      <td>Number => 1</td>
    </tr>
    <tr>
      <td>MaxSize</td>
      <td>The maximum size of the Auto Scaling group.</td>
      <td>4</td>
      <td>no</td>
      <td>Number => 1</td>
    </tr>
    <tr>
      <td>DrainingTimeoutInSeconds</td>
      <td>Maximum time in seconds an EC2 instance waits when terminating until all containers are moved to another EC2 instance (draining)</td>
      <td>600</td>
      <td>no</td>
      <td>Number from 60 to 86400</td>
    </tr>
    <tr>
      <td>StopContainerTimeoutInSeconds</td>
      <td>ime in seconds the ECS agent waits before killing a stopped container (see ECS_CONTAINER_STOP_TIMEOUT)</td>
      <td>300</td>
      <td>no</td>
      <td>Number from 30 to 3600</td>
    </tr>
    <tr>
      <td>ContainerMaxCPU</td>
      <td>The maximum number of cpu reservation per container that you plan to run on this cluster. A container instance has 1,024 CPU units for every CPU core.</td>
      <td>128</td>
      <td>no</td>
      <td>Number</td>
    </tr>
    <tr>
      <td>ContainerMaxMemory</td>
      <td>The maximum number of memory reservation (in MB)  per container that you plan to run on this cluster.</td>
      <td>128</td>
      <td>no</td>
      <td>Number</td>
    </tr>
    <tr>
      <td>ContainerShortageThreshold</td>
      <td>Scale up if free cluster capacity <= containers (based on ContainerMaxCPU and ContainerMaxMemory settings)</td>
      <td>2</td>
      <td>no</td>
      <td>Number => 0</td>
    </tr>
    <tr>
      <td>ContainerExcessThreshold</td>
      <td>Scale down if free cluster capacity >= containers (based on ContainerMaxCPU and ContainerMaxMemory settings)</td>
      <td>10</td>
      <td>no</td>
      <td>Number => 2</td>
    </tr>
    <tr>
      <td>ManagedPolicyArns</td>
      <td>Comma-delimited list of IAM managed policy ARNs to attach to the instance's IAM role</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
  </tbody>
</table>

## Outputs

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Export</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ModuleId</td>
      <td>The ID of module: `ecs-cluster`</td>
      <td></td>
    </tr>
    <tr>
      <td>ModuleVersion</td>
      <td>The version of module: `2.0.0`</td>
      <td></td> 
    </tr>
    <tr>
      <td>StackName</td>
      <td>The name of CloudFormation Stack</td>
      <td></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>The name of ECS Cluster</td>
      <td>`${AWS::StackName}-Name`</td> 
    </tr>
    <tr>
      <td>Arn</td>
      <td>The ARN of ECS Cluster</td>
      <td>`${AWS::StackName}-Arn`</td> 
    </tr>
    <tr>
      <td>SecurityGroupId</td>
      <td>The ID of SecurityGroup for ECS Cluster instances</td>
      <td>`${AWS::StackName}-SecurityGroupId`</td> 
    </tr>
  </tbody>
</table>
