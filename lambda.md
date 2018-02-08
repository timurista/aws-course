# lambda

history of cloud

-- data center
layers of abstraction ugly truth of what is running our stuff
- cloud someone else can do it, it's not fun we have to call someone. Order for DB server 10 day provisioning time
- ec3 you could provision machines with api calls
  - infrastructure as a service
  - aws is infrastructure as code
  - just using api calls

problem, still running on servers, you have to manage windows / linus, have to reinstall things

platform as a service, upload code then amazon would provision code underlying for you
  - same problem, you are still managing windows and linux
  - containers, docker -- how amazon docker ecs works
    - still have to deploy to server
    - response to load
  
## lambda introduced
no managing container, all you have to worry about is code
  you upload code
lambda application layer, aws api
  all you worry about is your code
  compute server
  - takes care of provisioning
  - event-driven compute source, responds to events. Bucket or dynamoDB table

lets say user uploads meme to s3, trigger event --> lambda takes our meme and encodes it to image then stores it to s3, which returns to user
SCALES AUTOMATICALLY
  - scales out -- you add more instances (like load balancing)
  - scales up ^ increase resources

Lambda triggers
- compute lambda

User browses in chrome
  http request -> api gateway -> lambda -> returns response

every time user sends request through api gateway and it is forwarded to lambda you have a new lambda instance

1 million free invocations per month
-> language supported?
lambda priced based on number of requests
  - 20cents per requests thereafter
  - paying as people request content
duration, time it returns
  - max threshold is 5 minutes

## WHy is it cool?
No servers
Continous Scaling
lambda up out not up automatically
s3, dynamnodb, lambda is serverless




