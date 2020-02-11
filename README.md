# ec2-node-server

Current deployment (02/11/2020)

Repo is (was) cloned at instance launch using user-data script.

Now only on use on: autostartNode AMI (ami-0813c5d331040ccc0, us-east-1) 
  - SG: WebDMZ, Node server
  - TargetGroup: targetgroup/myTargetGroup/bf2b5f42b4102674
  - ALB: arn:aws:elasticloadbalancing:us-east-1:680637963852:loadbalancer/app/myALB/a95ac2ea249864c2
    ALB will forward HTTP requests (:80) on Node Server (:3000)
  - DNS Endpoint: myALB-464643593.us-east-1.elb.amazonaws.com

Only manual deployment ATM...
e.g. SSH to the instance using .pem key -> Clone -> Copy snapshot -> Create AMI
```
ssh -i ~/.ssh/<keyName>.pem ec2-user@<Public Ip> 
```
