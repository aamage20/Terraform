## Blocks in Terraform ##
**1. Terraform Block** 
   - it is used to define global configure
   - setting specific version
   - configuring backend for storing the state file
   - defining experimental or optional feature

````
terraform{ 
    required_providers{ ### indicates the providers used in your configuration
        aws{
            source = "hashicrop/aws ## specifies provider namespace
            version = ">= 2.7.0" ## specifies  provider version
        }
    }
}
````