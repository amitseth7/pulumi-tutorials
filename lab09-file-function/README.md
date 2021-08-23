

# Creating EC2 instance web server on AWS by specifying user_data in apache-install.sh file. 

## Deploying and running the program

Note: some values in this example will be different from run to run.  These values are indicated
with `***`.

1. Create a new stack:

    ```
    pulumi stack init ec2-input-file
    ```

2. Set the AWS region:

    ```
    pulumi config set aws:region ap-south-1
    
    ```

3. Run `pulumi up` to preview and deploy changes.  After the preview is shown you will be
    prompted if you want to continue or not.

    ```  
Previewing update (ec2-input-file)


     Type                      Name                              Plan
 +   pulumi:pulumi:Stack       ec2-file-function-ec2-input-file  create
 +   ├─ aws:ec2:SecurityGroup  vpc-web                           create
 +   ├─ aws:ec2:SecurityGroup  vpc-ssh                           create
 +   └─ aws:ec2:Instance       my-ec2-vm-0                       create
 
Resources:
    + 4 to create

Do you want to perform this update?  [Use arrows to move, enter to select, type to filter]
```
> yes
  no
  details


    ```

4. Now, go to AWS console, navigate to EC2 service & check the ec2 instances with name "my-ec2-vm-0 ":
 
5. Open the site URL in a browser with publicIp of ec2 instance & see the output.

6. To clean up resources, run `pulumi destroy` and answer the confirmation question at the prompt.