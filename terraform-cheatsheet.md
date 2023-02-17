# Terraform Commands

## Terraform main commands

- `terraform init` - prepare your working directory for other commands
- `terraform validate` - check whether the configuration is valid
- `terraform plan` - show changes required by the current configuration
- `terraform apply` - create or update infrastructure
- `terraform destroy` - destroy previously-created infrastructure

## Terrafor main commands details
</p></details>

<details><summary>$ terraform init</summary><p>
        
```yml
Initializing the backend...

Initializing provider plugins...
- Reusing previous version of hashicorp/aws from the dependency lock file
- Using previously-installed hashicorp/aws v3.73.0

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
```
</p></details>

</p></details>
<details><summary>$ terraform validate</summary><p>

```yml
Success! The configuration is valid.
```
</p></details>

</p></details>
<details><summary>$ terraform fmt</summary><p>

```yml
ec2_instance.tf
```
</p></details>

</p></details>
<details><summary>$ terraform plan -out=jenkins-environment</summary><p>

```yml
erraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # aws_instance.web will be created
  + resource "aws_instance" "web" {
      + ami                                  = "ami-0c9978668f8d55984"
      + arn                                  = (known after apply)
      + associate_public_ip_address          = true
      + availability_zone                    = (known after apply)
      + cpu_core_count                       = (known after apply)
      + cpu_threads_per_core                 = (known after apply)
      + disable_api_termination              = (known after apply)
      .
      .
      .
      Saved the plan to: jenkins-environment
     To perform exactly these actions, run the following command to apply:
     terraform apply "jenkins-environment"
```
</p></details>




## All other commands

```
terraform console - Try Terraform expressions at an interactive command prompt
terraform  fmt - Reformat your configuration in the standard style
terraform  force-unlock - Release a stuck lock on the current workspace
terraform  get - Install or upgrade remote Terraform modules
terraform  graph - Generate a Graphviz graph of the steps in an operation
terraform  import - Associate existing infrastructure with a Terraform resource
terraform  login - Obtain and save credentials for a remote host
terraform  logout - Remove locally-stored credentials for a remote host
terraform  output - Show output values from your root module
terraform  providers - Show the providers required for this configuration
terraform  refresh - Update the state to match remote systems
terraform  show - Show the current state or a saved plan
terraform  state - Advanced state management
terraform  taint - Mark a resource instance as not fully functional
terraform  untaint - Remove the 'tainted' state from a resource instance
terraform  version - Show the current Terraform version
terraform  workspace - Workspace management
```

## Global options

```
terraform -help - Show this help output, or the help for a specified subcommand.
terraform -version - An alias for the "version" subcommand.
```