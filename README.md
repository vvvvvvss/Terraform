# Terraform
Deploy infrastructure  using Terraform
1. Scope - Identify the infrastructure for your project.
2. Author - Write the configuration for your infrastructure.
3. Initialize - Install the plugins Terraform needs to manage the infrastructure.
4. Plan - Preview the changes Terraform will make to match your configuration.
5. Apply - Make the planned changes.

## Declarative vs. Imperative

**Declarative programming** is a paradigm describing WHAT the program does, without explicitly specifying its control flow. There is zero chance of misconfiguration with declarative programming.  
* Declarative languages don't have looping control structures, e.g. for and while, because due to immutability, the loop condition would never change.    
* Declarative languages don't express control-flow other than nested function order (a.k.a logical dependencies), because due to immutability, other choices of evaluation order do not change the result.     
Declarative programming uses scripting languages such as JSON, YAML, XML.   

**Imperative programming** is a paradigm describing HOW the program should do something by explicitly specifying each instruction (or statement) step by step, which mutate the program's state.  
* Imperative programming is less verbose; you could end up with misconfiguration
* AWS CDK and Pulumi use imperative  
Imperative programming uses scripting languages such as Python, Ruby and Javascript.
  
*Terraform is declarative but it has imperative-like features like for loops, dynamic blocks, locals and complex data structures like maps and collections.  *

## Idempotent vs non-idempotent
**Idempotency** is a principle of IaC that refers to the state of a configuration after applying changes.  

**Non-idempotent** configurations will add the specified resources each time they are applied whereas idempotent configurations can be applied multiple times without changing the results.  

*Non-idempotent example:*  
Your configuration file specifies that you need three virtual machines. Each time you apply your configuration, you have 3 more virtual machines. So each time you apply, the number of VMs will increment by 3.  

*Idempotent example:*  
Your configuration file specifies that you need three virtual machines. Each time you apply your configuration, the number of virtual machines is always 3 virtual machines. So no matter how many times you apply, you will always have the same number of VMs in your configuration.  
