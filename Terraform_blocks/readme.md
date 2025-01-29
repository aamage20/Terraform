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
**2. Provider Block**
  - used to configure and define the provider for specific cloud or information.
  - In provider block we specify details such as provider name and version
  - their are two ways to define the provider block

  i. direct adding the access and sceret key in provider block

  ````
  provider "aws" {
  region = "us-west-2"
  access_key = " access-key"
  sceret_key = " sceret-key"
}

````

ii. adding the keys inside the profile with aws configure --profile profile_name. for security in terminal

````
provider "aws" {
  region = "us-west-2"
  profile = "profile_name"
}

````
**3. Resource Block**
     - The resource block is used to define the infrastructure components (like EC2 instances, storage, etc.) that you want to create and manage.

````
resource "aws_instance" "example" { ## example is the  logical name or identifier using inside the terraform
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}

````