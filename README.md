# Training
Reusing the pulumi docker project as a starting point.

## Stacks
- What are stacks and how are stacks/projects different?
- Common naming patterns for stacks
- Creating a stack - init
- Listing a stack - ls
- Selecting a stack
- Exporting a stack's state - export

## Stack Configurations
- Each stack can has it's own configuration and it's own unique set of values in Pulumi.{stack_name}.yaml
- Configuration values can be retrieved in code and also via the CLI. 
- get - useful for viewing config values
- set - allow you to set config values; --secret for secret values
- config - dumps the entire config; --secret to decrypt secrets as part 
- cp - copy one stack config to another stack
- get vs require - in code; defaults vs supplied values
- project level config vs stack level config

## Stack Outputs
- Outputs are values exporting from any given stack.
- Outputs are shown during updates, can be retrieved via the CLI, and are displayed in the Pulumi Service
- Common values exported from stacks are: resource ids, URLs, DNS names, Computed IP addresses, etc
- These can be usedful for running CLI commands that include those values. Eg- curl against a recently deployed api
- Another common use of stack outputs is using outputs from one stack as in puts to another. These inter-stack dependencies are accomplished via stack references.
- Show in code how to set stack exports
- Values can be directly from resources or derived.

## Stack References
- Based around stack outputs
- Allow access to the outputs of one stack from another stack. Interstack dependencies allows values to be shared programmatically, allowing more automation.
- Stack references can be viewed in the Pulumi Service as well.
- Create a second project to read in the stack ref of our main app and export it

## Secrets
- what is a Pulumi secret?
- encryption `--secret` - Pulumi asks you if something is secret, if it suspects
- setting secrets from config and using in code - get vs require
- what happens when something is marked as a secret?
- viewing config secrets from CLI

## Introduce the Pulumi Service and how all the above interacts
