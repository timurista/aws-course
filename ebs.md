# EBS

you can select ami based on
  region
    operating ssytem
      architecture
      launch permissions
    
    Instance store
    EBS backed volumes

EBS <-- actions stop it, and take instance
and instance store <-- cannot stop (reboot, but not stop)
  - critical difference
  - we can see health of instance
  - 
by default root volumes will be deleted on termination

## Elastic Load Balancer

Application Load Balancer
6 months old or so,
exam questions typically classic load balancer
  TCP layer, layer 4 load balancer

MyClassicLoadBalancer-1088485743.us-west-1.elb.amazonaws.com

point ec2 load balancer

application load balancer -- dns address to connect
  - listeners listening on port 80
  - you can track http errors
  - 404 etc / how to use aplication load balancers

Instances monitored by ELB are reported as either InService or OutOfService
Health Checks check the instance helath by talking to it
- Have your own DNS name, you can configure a domain to point there


