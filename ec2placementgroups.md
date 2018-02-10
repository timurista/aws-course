# Placement Group
grid computing, high network throughput, low network latency

10gbs network
cant span multiple availability zones
  - only in 1

only things like compute optimized, gpu, memory optimized, storage optimized

cant merge them
you add ec2 instances into these placement groups and they can generate higher throughput. can't move an existing instance in there, and they recommend homogeouns (same type) instances in placement grop
  - create ami from existing instance then move it into a placement group

