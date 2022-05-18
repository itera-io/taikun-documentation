---
tags:
  - Guidelines
  - Terraform
  - Provider
hide:
  - tags
---

# **Terraform Provider for Taikun Workshop**

[:fontawesome-solid-user:](../../user/projects/project-details-k8s/) **User**
[:fontawesome-solid-user-tie:](../../manager/projects/project-details-k8s/) **Manager**
[:fontawesome-regular-handshake:](../../partner/projects/project-details-k8s/) **Partner**

## **Introduction**

The purpose of this workshop is to introduce you to Terraform and the Terraform Provider for Taikun. The latter
will allow you to use Terraform to manage resources in Taikun.

## **Annotations**

- Text in this form is to be typed, as is, on the command line.

``` bash
cd workshop/
ls
echo Hello!
```

- This form of text shows screen output, usually the output of commands.

``` bash
task_00/
task_01/
...
Hello!
```

- This format is for code in Terraform’s configuration language, HashiCorp Configuration Language (HCL).

``` bash
resource "aws_instance" "example" {
  ami = "abc123"

  network_interface {
    ...
  }
}
```

- You may wish to skip reading information blocks if you are already familiar with Terraform and its configu-
ration syntax.

???+ Tip
    Some information about Terraform...

## **Setup**

To complete this workshop, you will need to install Terraform and the workshop files.
There are two ways to do this.
- If you wish to install Terraform and the workshop files locally, read Local setup.
- To use the provided Docker image which already contains everything you need.

### **Setup using Docker.**

#### **Local setup**
##### **Requirements**
- You must have Terraform version 0.14 or newer installed.
- You will need Git to clone the provider’s repo.

##### **Installing Terraform**
This Hashicorp tutorial explains how to install Terraform on OS X, Windows and Linux.

##### **Downloading the workshop files**
Clone the workshop directory and switch into the workshop/ directory.

``` bash
git clone https://github.com/itera-io/terraform-provider-taikun-workshop.git
cd terraform-provider-taikun-workshop/workshop/
```

#### **Setup using Docker**

##### **Requirements**

You must have Docker and Git installed.

##### **Setup**

Start by cloning the workshop repository.

``` bash
git clone --recursive https://github.com/itera-io/terraform-provider-taikun-workshop.git
```

### **Docker image creation**

You’ll need to build the image, this operation can take several minutes.

``` bash
DOCKER_BUILDKIT=1 docker build --rm --target bin -t tf-workshop .
```

### **Docker container creation**

To create the Docker container, run one of the following commands from the root of
*terrraform-provider-taikun-workshop*.

- On Windows, run the following command in the command prompt (not Powershell).

``` bash
docker run -v %CD%/workshop:/root/workshop --name tf-workshop -it tf-workshop
```

• On Linux and MacOS:

``` bash
docker run -v $(pwd)/workshop:/root/workshop --name tf-workshop -it tf-workshop
```

This will mount the workshop/directory in the Docker container and log you in to the container as root. In other
words, you will need to run terraform commands from within the container shell, however you can edit the files
in workshop/directory with the editor of your choice on your machine.

#### **Restarting the Docker container**

You can exit the container at any time without losing your progress. If you have exited the Docker container, run
the following command to restart it.

``` bash
docker start -i tf-workshop
```

#### **Text editing within the container**

If you wish to edit the files in workshop/directory from within the container, the Docker image has the vim, micro and
nano packages installed. If you are unfamiliar with Nano and Vim keybindings, the Micro editor has traditional
Common User Access keybindings (Ctrl-C for copy, Ctrl-Z for undo, etc).

## **Documentation**
The provider documentation is available on the Terraform Registry.

## **Tasks**

The end goal of this workshop is to have an operational Taikun project built solely with Terraform configuration
files. By following a step by step process, you will discover how various Taikun resources are declared and
managed using Terraform.

All your work will be done in the workshop/directory. These are its initial contents.

``` bash
./workshop/
|-- main.tf
|-- taikun_auth.auto.tfvars
|-- variables.tf
```

*main.tf* contains the Provider configuration, namely its source address and what credentials to use. You will
not need to edit this file.

```
# main.tf
terraform {
  required_providers {
    taikun = {
      source = "itera-io/taikun"
      version = "1.0.0"
    }
  }
}

provider "taikun" {
  email = var.taikun_email
  password = var.taikun_password
}
```

Terraform reads its configuration from all the files with the extension *.tf*, in the working directory. Having the
provider configuration in *main.tf* is simply a convention.

During this workshop, each task should be coded in a separate config file. At the end of the workshop, your
directory will be organized as such

```
./workshop/
|-- main.tf
|-- taikun_auth.auto.tfvars
|-- task0.tf
|-- task1.tf
|-- task2.tf
|-- task3.auto.tfvars
|-- task3.tf
|-- task4.tf
|-- task5.tf
|-- task6.tf
|-- task7.tf
|-- variables.tf
|-- users.auto.tfvars
|-- users.tf
```

### **Authentication**
In order to complete the tasks that follow, you will need to provide Taikun credentials to Terraform. You will need
a Partner account as some of the tasks, such as creating an organization, require Partner privileges.
Input variables will be explained later in the workshop. For now, simply edit *taikun_auth.auto.tfvars* and
replace the values of *taikun_email* and *taikun_password* with your credentials.

``` bash
# taikun_auth.auto.tfvars
taikun_email = "jane.doe@itera.io"
taikun_password = "PassWord123"
```

To find out more about providing sensitive data to Terraform, see this Hashicorp tutorial.

### **Task 0: Organization**

???+ Note
    For this task, please write your code in the file 'task0.tf' at the root of the workshop/directory.

This objective of this first task is to create an organization. All resources created in the future will be part of this
organization. As this is the first task, every step of the process is documented.

Before you do anything, start by preparing your working directory for other commands.
terraform init

???+ Tip
    terraform init only needs to be run once when starting a new project or after updating the list of
    providers to use.

If all went well, you should see the following message.

``` bash
Initializing the backend...
[...]
Terraform has been successfully initialized!
```

Once Terraform has been initialized correctly, you can declare your organization resource. Create 'task0.tf' and
write the following configuration block to it.

``` tf
resource "taikun_organization" "myorg" {
  name = "<name>"
  full_name = "<full-name>"
  discount_rate = 120
}
```

Be sure to replace <name> and <full-name> with names of your choosing. You can also choose another label
instead of myorg.

???+ Tip
    Notice the syntax of the configuration block, as you are creating a resource, it begins with the keyword
    resource, followed by its type between double quotes. 

    The type of resource is always lowercase and prefixed by the name of the provider, thus "taikun_organization".

    Following the resource’s type is a label, it must be unique for this type of resource, and is used to refer to this specific resource, as you will
    find out later. 

    Watch out, this label does not correspond to the name of the resource in Taikun

    Three arguments are then defined: name, full_name and discount_rate. On the left side of the equals
    sign is the argument’s identifier, on the right is its value. 

    See the documentation of Taikun’s organization resource for a full list of arguments, i.e. the resource’s schema.

    Labels and argument names can contain letters, digits, underscores and hyphens and may not start with
    a digit.

Run the following command to reformat your configuration in the standard style.

``` bash
terraform fmt
```

Now apply your changes.

???+ Tip
    If you have already created resources, apply will refresh Terraform’s state by making request to Taikun’s
    API. If you wish to check the validity of your changes without refreshing the state, you can run terraform
    validate.

```
terraform apply
```

You should get a validation error.

```
Error: expected discount_rate to be in the range (0.000000 - 100.000000), got 120.000000
Now fix the discount rate so it is in the range 0-100 and run apply once more. Terraform will display a list of
resources to create. After checking the plan is correct, type yes to execute it.
```

???+ Tip
    You should notice a file terraform.tfstate in your working directory, Terraform uses this file to keep
    track of the state, do not modify or delete it.
    You may now list the resources in Terraform’s state.

```
terraform state list
```

You can also display their content.

```
terraform show
```
```
taikun_organization.myorg:
resource "taikun_organization" "myorg" {
    created_at = "2021-11-05T14:00:50Z"
    discount_rate = 42
    full_name = "Jane Doe's organization"
    id = "6383"
    is_read_only = false
    lock = false
    managers_can_change_subscription = true
    name = "my-organization"
    partner_id = "119"
    partner_name = "TF-CI"
    projects = 0
    servers = 0
}
```
You may wish to check the organization was indeed created at app.taikun.cloud/organizations.

???+ Tip
    Try running terraform apply again, Terraform will refresh its state, and, as long as nothing has
    changed, tell you that no changes are needed.
    
    You can also try deleting the organization through the web UI and running terraform apply. Terraform
    will tell you that changes have occured outside of Terraform and recreate the resource

### **Task 1: Kubernetes Profile**
???+ Note
    For this task, please write your code in the file task1.tf at the root of the workshop/directory.

Now that you have created an organization, you will create a Kubernetes profile belonging to it. Check the
kubernetes_profile resource’s schema on the provider’s documentation and declare the resource in task1.tf.
Set *organization_id* to the ID of the organization created in the previous task (see Task 0: Organization).

Feel free to set some of *kubernetes_profile’s* other optional attributes, such as *schedule_on_master* and
*load_balancing_solution*.
Once you have declared your resource, apply your changes and move on to the next task.

???+ Tip
    To refer to the ID of your organization, use the following syntax.
    resource.taikun_organization.myorg.id
    Make sure to replace myorg if you used another label for your organization.

### **Task 2: Slack Configuration & Alerting Profile**

???+ Note
    For this task, please write your code in the file task2.tf at the root of the workshop/directory.

You will now create an alerting profile using a Slack configuration.

  1. Start by declaring a Slack configuration. Here is its documentation.

     Its hook URL should be https://hooks.myapp.example/ci. It must send alert-type notifications only
     to the channel ci.

  2. You can now declare the alerting profile. Here is its documentation.
     The alerting profile should send notifications daily using the Slack configuration declared above.

???+ Important
    As always, your resources should belong to the organization created in Task 0: Organization.

Once you have declared these two new resources, apply your changes and move on to the next task.

### **Task 3: Cloud Credentials**

???+ Note
    For this task, please write your code in the file *task3.tf* at the root of the workshop/directory.
    You will also be editing *task3.auto.tfvars*.

???+ Important
    You will need OpenStack credentials to complete this task.

Cloud credentials are needed to create a Taikun project. In a real work environment, cloud credentials should
not be stored under version control Terraform’s input variables help solve this problem.

Variables are declared in *variables.tf* by convention. This file declares the variables *taikun_email* and
*taikun_password* used for authentication.

```
# variables.tf
variable "taikun_email" {
  description = "Taikun email"
  type = string
  sensitive = true
}

variable "taikun_password" {
  description = "Taikun password"
  type = string
  sensitive = true
}
```

???+ Tip
    Input variables are declared with a variable block. The label that follows the variable keyword is the
    name of the variable.
    
    • The description argument is used to specifiy the variable’s documentation.
    • type is the type of this argument’s value.
    • If set to true, sensitive will hide this variable’s value in Terraform output. It defaults to false.

    To know more about input variables and a full list of arguments, see the Terraform documentation on
    variables.

    Variables are then defined in .tfvars files, as seen in subsection Authentication.

For the sake of simplicity, variables will be declared in the task/*.tf files. Thus, in *task3.tf*, insert the following
variable declarations

```
variable "openstack_url" {
  description = "OpenStack url"
  type = string
  sensitive = true
}
variable "openstack_user" {
  description = "OpenStack user"
  type = string
  sensitive = true
}
variable "openstack_password" {
  description = "OpenStack password"
  type = string
  sensitive = true
}
variable "openstack_domain" {
  description = "OpenStack domain"
  type = string
  sensitive = true
}
variable "openstack_region" {
  description = "OpenStack region"
  type = string
}
variable "openstack_public_network" {
  description = "OpenStack public network"
  type = string
}
variable "openstack_project" {
  description = "OpenStack project name"
  type = string
}
```

???+ Note
    If copy-pasting this code block into *task3.tf* does not indent the code properly, save *task3.tf* and run
    terraform fmt.

Now that the OpenStack variables have been declared, define the variables in *task3.auto.tfvars* using your
credentials.

Terraform must be told through command line arguments which .tfvars files to read. However, if variable
definition files have the extension .auto.tfvars, as is the case with taikun_auth.auto.tfvars, Terraform
will automatically fetch the variables’ values.

???+ Tip
    As a reminder, here is the syntax used in taikun_auth.auto.tfvars to define the variables
    taikun_email and taikun_password.
    
    ```
    taikun_email = "jane.doe@itera.io"
    taikun_password = "PassWord123"
    ```

???+ Tip
    In order to get a variable’s value, use the syntax var.<variable_name>. For example, the following line
    sets the OpenStack domain in the *cloud_credential_openstack* resource.
     
    ```
    domain = var.openstack_domain
    ```

Once you have declared your new resource, apply your changes and move on to the next task.

???+ Important
    As always, your resources should belong to the organization created in Task 0: Organization

### **Task 4: Users**

???+ Note
    For this task, please write your code in the file *task4.tf* at the root of the workshop/directory.
    You will also be *editing users.tf* and *users.auto.tfvars*.

You will now add users to the Taikun organization. As the organization could have a large amount of users, you
will use variables and the keyword *for_each* to avoid declaring multiple *taikun_user* blocks.

Add the following variable declaration to *users.tf*.

```
variable "users" {
  type = map(object({
    email = string
    role = string
   }))
   description = "List of project users"
   default = {}
}
```

The users variable is of a complex type: a map of objects with two arguments, email and role. The keys of the
map are strings, they will be the usernames of the users. The default = {} argument definition tells Terraform
that the default value of var.users is an empty map.

Here is an example definition of the users variable.

```
users = {
  "alice" = {
    email = "alice@gmail.com"
    role = "Manager"
  },
  "bob" = {
    email = "bob@gmail.com"
    role = "User"
  },
}
```

In this example, user accounts are defined for Alice and Bob.
  • Alice has a Manager account with the username alice and the email *alice@gmail.com*.
  • Bob has a User account with the username bob and the email *bob@gmail.com*.

Now edit users.auto.tfvars and define three users.
  • <name>-manager with Manager role and the email <name>-manager@mail.example.
  • <name>-user1 with User role and the email <name>-user1@mail.example.
  • <name>-user2 with User role and the email <name>-user2@mail.example.

Replace <name> with a name of your choosing.

You can now declare the user resource in task4.tf, the users must belong to the organization created in
Task 0: Organization. Here is its documentation. By using the *for_each* keyword, only one
resource block is needed.

???+ Tip
    Here is an example using the for_each keyword. Consider a Terraform provider to order pizzas. Sup-
    pose the variable pizza_orders has the following definition.

```
pizza_orders = {
  "alice" = {
    type = "pepperoni"
    size = "large"
   },
   "bob" = {
     type = "amatriciana"
     size = "medium"
   },
}
```

Here is how it would be used with the *for_each* keyword in a pizza_order resource.

```
resource "pizza_order" "orders" {
  for_each = var.pizza_orders

  client = each.key
  type = each.value.type
  size = each.value.size
}
```

You can also have a look at Terraform’s for_each documentation.

Once you have declared the user resource, apply your changes and move on to the next task.

### **Task 5: Access Profile**

???+ Note
    For this task, please write your code in the file task5.tf at the root of the workshop/directory.
    You will also be editing users.tf and users.auto.tfvars.

Before creating your first project, you will need an access profile.

The access profile must contain SSH keys for all the users created in the previous task, Task 4: Users. 
Rather than declare the SSH keys in a separate variable, you will add them to the users variable to
declare them on per user basis.

Modify users’s declaration in users.tf to include a list of SSH users per user.

```
variable "users" {
  type = map(object({
    email = string
    role = string
    ssh_users = list(object({
      name = string
      public_key = string
    }))
   }))
   description = "List of project users"
   default = {}
}
```

You can now edit *users.auto.tfvars* and define a list of SSH users for each user. Considering the previous
example of Alice and Bob, here is the same definition of users with added SSH users.

```
users = {
  "alice" = {
    email = "alice@gmail.com"
    role = "Manager"
    ssh_users = [
      {
        name = "alice-work"
        public_key = "ssh-ed25519 AAAATHEQUICKBROWNFOXJUMPEDOVERTHELAZYDOG example"
      },
      {
        name = "alice-home"
        public_key = "ssh-ed25519 AAAATHEQUICKBROWNFOXJUMPEDOVERTHELAZYDOG example"
      }
     ]
    },
    "bob" = {
      email = "bob@gmail.com"
      role = "User"
      ssh_users = [
        {
          name = "bob-laptop"
          public_key = "ssh-ed25519 AAAATHEQUICKBROWNFOXJUMPEDOVERTHELAZYDOG example"
        }
       ]
      },
     }
```

Add as many SSH users as you wish to the users defined in the previous task. Of course, you will need to use
valid SSH keys. If you do not wish to create your own, here is a public key value you can use:

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIB/8P0zXmI/Il81+/fnvGrf0X/VyNTrOJ9nQCxBxjc5m taikun
```

???+ Important
    Within one access profile, the names of SSH users must be unique.

You can now declare the taikun_access_profile resource in *task5.tf*. You will use for_each in a slightly
different manner as ssh_user is a nested resource within the access_profile resource. Here is the documen-
tation of the access profile resource.

The access profile’s requirements are:
   • It should use the DNS servers 8.8.8.8 and 1.1.1.1.
   • It should use the NTP server time.windows.com.
   • It should include all the SSH users defined in users.auto.tfvars.

???+ Tip
    While reading access profile’s schema, you may notice dns_server and ntp_server are of the type
    Block List.

    Going back to the pizza order example, here is how block lists are used. Suppose the pizza_order
    resource has an argument extra_topping defined as such:
        
         - extra_topping (Block List, Max: 5) List of extra pizza toppings. (see below for nested
         schema)

         Nested Schema for extra_topping
         Required:
         - name (String) Name of the extra topping
         - quantity (Number) Quantity

     Here is how Alice could add mozzarella di bufala and basil to her amatriciana pizza order.

     ```
     resource "pizza_order" "orders" {
       client = "alice"
       type = "amatriciana"
       size = "large"

       extra_topping {
         name = "basil leaves"
         quantity = 8
       }
       extra_topping {
         name = "bufala slices"
         quantity = 4
       }
     }
     ```

???+ Note
    The code to define the SSH users of the access profile is provided below. However, if you wish to give it
    a go yourself first, here is how.

    To define the ssh_user argument, you will need to use a dynamic block with the for_each keyword. You
    will also need to extract the list of all SSH users from the users variable. for expressions and the flatten
    function will be of use.

Spoiler ahead!

Solution:
Add the following dynamic "ssh_user" block to your access profile’s configuration.

```
resource "taikun_access_profile" "..." {

   # Rest of configuration: DNS servers, NTP servers, etc.
   # ...

   dynamic "ssh_user" {
     for_each = flatten([for user in var.users : user.ssh_users])
     content {
       name = ssh_user.value.name
       public_key = ssh_user.value.public_key
     }
    }
}
```

Once you have fully declared the access profile resource, apply your changes and move on to the next task.

### **Task 6: Project**

???+ Note
    For this task, please write all your code in the file task6.tf at the root of the workshop/directory.

Finally, you can declare a project resource. However, as flavors must be bound to the project, you must first fetch
a list of suitable flavors.

To do this, declare a flavors datasource. Datasources, as opposed to resources, only fetch information from
providers and do not create any resources. Add the following block to *task6.tf*.

```
data "taikun_flavors" "small" {
# FIXME
}
```

???+ Tip
    As you are declaring a datasource and not a resource, the block begins with the keyword data instead
    of resource. Once again, the type of datasource is in lowercase and must be prefixed by the name of
    the provider. Finally, the label "small" is used to designate this datasource.

Edit the datasource to search for flavors with 4 or fewer CPUs and no more than 8GB of RAM. Set its cloud
credential ID to that of the cloud credential created in Task 3: Cloud Credentials.

Then declare a local value flavors to be the list of names of the flavors read by the datasource. See the
Terraform documentation to know more about local values.

```
locals {
  flavors = [for flavor in data.taikun_flavors.small.flavors : flavor.name]
}
```

This will allow you to refer to the list of flavor names with local.flavors, which will be useful when defining the
project.

You now have everything you need to create a project in Taikun. Here is its documentation.

These are the requirements for the project resource:
  • As all previous resources, it must belong to the organization created in Task 0: Organization.
  • It must use the kubernetes profile defined in Task 1: Kubernetes Profile.
  • Its alerting profile must be the one defined in Task 2: Slack Configuration & Alerting Profile.
  • It should use the cloud credentials defined in Task 3: Cloud Credentials.
  • Monitoring must be enabled.
  • It should have one bastion, one kubemaster and one kubeworker.

???+ Tip
    To access the first element of a list, use the syntax list[index]. For example, to get the first flavor read
    by the flavors datasource, use *local.flavors[0]*.

After creating a project with Terraform, one may want to know its access IP. Once you have declared the project
resource, add the following output block to *task6.tf*.

```
output "project_access_ip" {
  value = resource.taikun_project.<project-label>.access_ip
}
```

Make sure to replace <project-label> with the label you gave your project. This will display the project’s
access IP once it has been created.-

???+ Tip
    Output values are a way for the user to output a specific value from Terraform’s state.
    
    An output value block begins with the keyword output followed by a unique label. By setting the value
    argument, the user can decide which value to output.
    
    To know more about output values, see Terraform’s documentation.

You can now apply your changes; expect to wait about 30 minutes for your project to be in Ready state.

### **Task 7: Project User Attachments**

???+ Note
    For this task, please write all your code in the file task7.tf at the root of the workshop/directory.

Now that your project is in Ready state, you can attach some users to it.

Declare a project user attachment resource with the following *for_each* argument, replacing <label> with the
label you gave the taikun_user resource.

```
for_each = {
  for user in resource.taikun_user.<label> : user.id => user
  if user.role == "User"
}
```

With this block, you will be able to attach only users with the User role to the project. To know more about this
syntax, see the documentation on for expressions.

Finally, set the proper values for the *user_id* and **project_id arguments and apply your changes.
