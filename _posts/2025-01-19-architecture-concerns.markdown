---
layout: post
title:  "Architecture Concerns"
date:   2025-01-19 00:00:00 +0000
categories: fundamentals
---
To create lasting timeless solutions an architect must take multiple factors into consideration. In the case of classical architecture these factors may include the environment, materials, construction technuiqes, and of course the overall feasability and cost of creation as well as maintenance.

Technical architecture is no different, except of course for the specific factors of concern.

## Performance & Scalability
Despite the cost of computing resources dramatically decreasing over the decades, the exponential increase in demand for digital solutions is large enough that it's not a feasable solution to simply throw money and resources at a system to scale it. Performance concerns must be considered early in the design of system and take into account future growth and scalability.

# Latency
Gamers of the early internet are very familiar with the term 'Lag', and to a lesser extent later generations may associate the term with buffering of streaming services. Essentially 'Lag' is a term used to describe high latency, think of it as what a physician is measuring when banging your knee with a rubber hammer: the greater the time to react the greater the latency or 'Lag'. Thinking in terms of a person's need to get from point A to B, latency may be reduced by electing to travel in a vehicle on a highway. A good architect will design the system to minimize Latency/Lag.

# Throughput
Throughput is another performance benchmark which refers to how much a system can proccess within a fixed amount of time. In keeping with the example of persons traveling from point to point, throughput may be thought of the number of people onboard: so a city bus has more throughput than a van which has more throughput than a sedan which has more throughput than a motorcycle. Modern networks have orders of magnitude more throughput than was available in previous generations, however this increased capacity has simply moved the performance bottleneck off the network and into the software systems sitting on them. A good architect will design the system to maximize throughput while minimmizing latency.

# Scalability
Scalability refers to a system's capability to grow to service elevated load without impacting Latency or Throughput. Traditional systems, sometimes called monoliths, can only be scaled vertically, which is another way of saying that resources must be added to the hardware on which they run in order to increase their capacity to service additional load without hampering latency or throughput. In contrast, modern applications are designed to be scaled horizontally, meaning additional worker instances may be introduced into the resource pool in order to meet the higher demands, which may be handled dynamically, automatically, and without downtime.

Vertical scaling can seldom be performed without introducing downtime, is expensive, and has realistic limits as to the capacity at which a system can scale. Lets take for example a monothically designed service chatbot which has functionalities to interact with a user via a chat interface and perform actions like troubleshooting a complex software system or shifting traffic for said system. The marketing departments of cloud services providers may try to convince developers that their Virtual Machine offerings are vertically scalable, which isn't necessarily an outright lie, however scaling the example chatbot on such a VM could prove very expensive to scale, and again cannot be done easily without downtime (one may stand up an identical VM and route traffic to it while the original's running workloads complete, scale up the original, move traffic back, then tear down the spare).

Horizontal scaling is the addition of workers to the pool, and is a very popular choice for modern applications which are built around the principle of loose coupling. Platforms like kubernetes and cloudfoundry where applications run in containers sitting behind platform managed load balancers make horizontal scaling as trivial as increasing instance counts of the underlying containers. Though to be fair, they also make vertical scaling as easy as increasing the resource quoatas allocated to each container... with the caveat that typically there's a fairly modest cap to the amount of resources which may be allocated to any one container. Modern platforms and applications are designed around the concept of clustering, and may be horizontally scaled by adding nodes to the cluster. Scaling horezontally is virtually infinately scalable and significantly less cost prohibitive than vertical scaling because it may be acheived by adding modest resources. This may best be visualized by thinking of storage as the resource to be scaled, petabyte hard drives may not yet be available and will likely be fairly expensive when first introduced, however petabyte scale storage may currently be acheived through pooling together drives whose capacity is in the terabyte range.

## Availability
In a world where everyone is always connected availability often takes center stage and software system designers must take into account their system availability when going to market. Availability of course is just as it sounds, the inverse of downtime, measured in percentage popularized by the quantity of nines. One 'nine' availability means an uptime of 90 percent, 3 'nines' 99.9 percent, and so forth, driven by Amazon's marketing department which claims 9 'nines' of availability for many of their popular and critical service offerings.

# Service Level Agreement (SLA)

# Mean Time Between Failures (MTBF)

# Busines Impact Analysis (BIA)

## Recoverability
# Recovery Time Objective (RTO)
# Recovery Point Objective (RPO)

## Operability & Maintainability
# Operability
# Maintainability

# Security

## Sustainability