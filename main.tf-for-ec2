provider "aws" {
  region = "ap-south-1"
}

resource "aws_instance" "example" {
  ami           = "ami-0c1a7f89451184c8b" # Amazon Linux 2 AMI (replace with valid AMI in ap-south-1)
  instance_type = "t2.micro"

  tags = {
    Name = "Terraform-EC2-Test"
    Environment = "Test"
    app = "myapp"
    dep = "database"
  }
}

terraform {
  backend "s3" {
    bucket         = "my-terraform-shaikbucket"
    key            = "ec2/terraform.tfstate"
    region         = "ap-south-1"
    #    dynamodb_table = "terraform-locks"
    encrypt        = true
  }
}
