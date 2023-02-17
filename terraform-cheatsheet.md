## Terraform

### Terraform main commands


- `terraform init` - prepare your working directory for other commands
- `terraform validate` - check whether the configuration is valid
terraform plan - show changes required by the current configuration
terraform apply - create or update infrastructure
terraform destroy - destroy previously-created infrastructure

### All other commands

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

### Global options

```
terraform -help - Show this help output, or the help for a specified subcommand.
terraform -version - An alias for the "version" subcommand.
```