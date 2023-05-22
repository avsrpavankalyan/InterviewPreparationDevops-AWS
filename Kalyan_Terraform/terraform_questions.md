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

3. How do you Move state from one Source to Another ?
   
    1. First, you need to configure the new backend where you want to move the state. That could be a different remote storage system,  such as an S3 bucket or Azure Storage, or a different backend type altogether.
    2. Initialize the new backend: Run the terraform init command with the -reconfigure "terraform init -reconfigure"
    3. Move the state: To move the state from the old source to the new one, you can use the terraform state command
       If you're using a remote backend, you can use the "terraform state pull" command to get the current state from the old source and then use "terraform state push" to store it in the new backend.
    4. If you're migrating to a local backend, you can use the "terraform state mv" command to move resources one by one from the old backend to the new one
