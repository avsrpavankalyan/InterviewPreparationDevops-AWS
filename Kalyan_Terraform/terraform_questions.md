Terrafrom Interview Questions 
-----------------------------

1. what do you mean by Terragrunt ?
   Terragrunt is an open-source configuration management tool which is commonly used in terraform.
   It adds additional functionality and simplifies the Management of terraform Configurations and Deployments by offering an thin wrapper around terraform commands 
   Terragrunt provides extra tools to keeping your configurations DRY ( here dry means dont repeat your self)
   Terragrunt Helps to automate and smooth usage of terraform by providing features such as 
     1. Configuration reusability:
           With Terragrunt, you can define reusable Terraform modules that encapsulate common infrastructure patterns and configurations, promoting code reuse and reducing duplication.  
     2. Remote State Management:
           Terragrunt supports storing the Terraform state remotely, enabling multiple team members to work on the same infrastructure simultaneously
     3. Dependency Management:
           Terragrunt enables you to define dependencies between Terraform modules, ensuring that they are deployed in the correct order to satisfy any interdependencies.
     4. Environment Management:
           It simplifies managing different environments (e.g., development, staging, production) 

2. What is Null Resource in Terraform ?
   In Terraform, a "null_resource" is a resource type provided by Terraform itself that serves as a placeholder resource. It doesn't represent any physical infrastructure or interact with any external service directly( ex. Cloud platforms ) but  it can be used to define Random actions or behaviors within a Terraform configuration.
   It allows you to execute local provisioners, triggers, or external commands without creating any actual infrastructure resources.
    --> Basically terraform null resource will not create anything it will be empty.
    --> It will not contain any terraform state. that means the null resource which is created that will not have any record or Data    in terrafrom state. 
   Terraform null resource can be used in 
     1. run any shell scripts or commands.
     2. can be used in Terraform Module, Terraform count, Terraform Data source.
     3. Use with output blocks.
