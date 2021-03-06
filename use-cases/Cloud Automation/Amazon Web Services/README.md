Amazon Web Services
===================

* 1 [Amazon Web Services recommendations and specific behaviours](#amazon-web-services-recommendations-and-specific-behaviours)
* 2 [Authentication in AWS](#authentication-in-aws)
* 3 [Usage](#usage)

Amazon Web Services recommendations and specific behaviours
-----------------------------------------------------------

| :warning: Please read this carefully before running our service in production on Amazon Web Services.|
|:-----------------------------------------------------------------------------------------------------|

We recommend using a network (level 4) load balancer to allow direct TCP connections to the WAF instances.

AWS health checks (in **aws_lb_target_group**) cannot provide a **Host** HTTP header, reverse proxies must not block unknown hosts.

Authentication in AWS
---------------------

Export AWS parameters for Terraform (access and secret key for your Amazon account):

```
export TF_VAR_access_key=XXXXX
export TF_VAR_secret_key=XXXXX
```

You can also add them directly in the appropriate **main.tf** file.

For more details about the authentication of Terraform with AWS see: https://www.terraform.io/docs/providers/aws/index.html.

Usage
-----

Terraform modules for AWS and some examples are provided on [github.com/Rohde-Schwarz](https://github.com/Rohde-Schwarz/r-s-waf-extra/tree/master/terraform).

Modules are located in:

* **modules/aws/autoscaled**: module to deploy an autoscaled R&S®Web Application Firewall cluster.
* **modules/aws/basic**: module to deploy a basic R&S®Web Application Firewall cluster.
* **modules/aws/lb**: basic implementation of AWS ELB for an R&S®Web Application Firewall cluster (basic or autoscaled).
* **modules/aws/policy**: basic implementation of autoscaling policies for an autoscaled R&S®Web Application Firewall cluster.

Examples for AWS can be found in:

* **examples/aws_basic**: shows how we deploy a basic R&S®Web Application Firewall cluster with an AWS ELB.
* **examples/aws_autoscaled**: shows how we deploy an autoscaled R&S®Web Application Firewall cluster with an AWS ELB and some autoscaling policies.

In the main configuration file, **main.tf**, you can edit variables like access and secret key, AWS region and prefix of your future instances. You can also find every configuration needed to deploy your instances.

| :warning: Don't forget to edit the template to match your configuration before using it.|
|:----------------------------------------------------------------------------------------|
