# Cloud Security with AWS IAM

## Introduction

This project demonstrates how to securely manage access to AWS resources using **AWS IAM** (Identity and Access Management). The objective is to create IAM users, groups, and roles, apply fine-grained access controls, and use policies to ensure security and scalability in a cloud environment.

## Features

- **IAM Users and Groups**: Create and manage users and user groups for secure access.
- **IAM Policies**: Define and implement policies for specific access permissions.
- **EC2 Instance Management**: Launch and manage EC2 instances, using tags for easy identification and access control.
- **Tagging**: Implement tags for resources to organize and control access based on environment types (e.g., development, production).
- **Testing IAM Policies**: Test IAM policies to verify access controls for different environments (development vs production).

## Project Setup

### Prerequisites

Before using this project, ensure you have the following:
- **AWS Account**: Access to an active AWS account.
- **IAM Permissions**: Sufficient IAM permissions to create users, groups, policies, and manage EC2 instances.
- **AWS CLI**: Optionally, AWS CLI set up to interact with resources from your terminal.

### Steps to Use:

1. **Create IAM Users**:  
   Create IAM users to manage access to AWS resources.

2. **Create IAM Groups**:  
   Organize users into groups and assign permissions based on roles.

3. **Create IAM Policies**:  
   Write policies (using JSON) to define who can access what resources. Example policy:
   - Allow users to start/stop EC2 instances in the **development** environment while denying tag modification across instances.

4. **Assign Tags to Resources**:  
   Tag EC2 instances with environment labels (`env = development`, `env = production`) to manage access efficiently.

5. **Test IAM Policies**:  
   Test the IAM policies by attempting to stop EC2 instances. For example, stopping an instance tagged with `env = production` will be denied if the user doesn’t have the required permission.

## Key Concepts

### IAM Users, Groups, and Roles:
- **IAM Users**: Individuals or applications that need access to AWS resources.
- **IAM Groups**: A way to manage users collectively by assigning permissions to groups.
- **IAM Roles**: Used by AWS services or external users to perform specific tasks or actions within your AWS account.

### IAM Policies:
- **Policy**: A set of rules that define allowed or denied actions for specific resources. Policies are written in JSON format and specify **Effect**, **Action**, and **Resource**.

### EC2 Instance Tags:
Tags are used to organize and identify resources in AWS. In this project, the `env` tag is used to differentiate between **development** and **production** environments.

## Testing IAM Policies

1. **Stopping EC2 Instances**:
   - **Development Instance**: Allowed to stop EC2 instances tagged with `env = development`.
   - **Production Instance**: Denied permission to stop instances tagged with `env = production` to enforce access control.

## Conclusion

In this project, you learned how to:
1. Launch EC2 instances and apply tags.
2. Set up IAM policies to restrict access based on environment tags.
3. Create IAM users and groups for managing permissions.
4. Test IAM policies to ensure secure access control.

## Additional Resources
- [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/)
- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)
- [AWS Tagging Best Practices](https://docs.aws.amazon.com/resourcegroupstaggingapi/latest/userguide/tagging-best-practices.html)
