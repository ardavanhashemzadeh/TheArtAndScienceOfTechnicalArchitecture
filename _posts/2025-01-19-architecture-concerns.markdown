---
layout: post
title:  "Architecture Concerns"
date:   2025-01-19 00:00:00 +0000
categories: fundamentals
---
To create lasting timeless solutions an architect must take multiple factors into consideration. In the case of classical architecture these factors may include the environment, materials, construction technuiqes, and of course the overall feasability and cost of creation as well as maintenance.

Technical architecture is no different, except of course for the specific factors of concern.

## Performance & Scalability
Despite the cost of computing resources dramatically decreasing over the decades, the exponential increase in demand for digital solutions is large enough that it's not a feasable solution to simply throw money and resources at a system to scale it. Performance concerns must be considered early in the design of systems and take into account future growth and scalability.

# Latency
Gamers of the early internet are very familiar with the term 'Lag', and to a lesser extent later generations may associate the term with buffering of streaming services. Essentially 'Lag' is a term used to describe high latency, think of it as what a physician is measuring when banging your knee with a rubber hammer: the greater the time to react the greater the latency or 'Lag'. Thinking in terms of a person's need to get from point A to B, latency may be reduced by electing to travel in a vehicle on a highway. A good architect will design the system to minimize Latency/Lag.

# Throughput
Throughput is another performance benchmark which refers to how much a system can proccess within a fixed amount of time. In keeping with the example of persons traveling from point to point, throughput may be thought of the number of people onboard: so a city bus has more throughput than a van which has more throughput than a sedan which has more throughput than a motorcycle. Modern networks have orders of magnitude more throughput than was available in previous generations, however this increased capacity has simply moved the performance bottleneck off the network and into the software systems dependant on them. A good architect will design the system to maximize throughput while minimmizing latency.

# Scalability
Scalability refers to a system's capability to grow to service elevated load without impacting Latency or Throughput. Traditional systems, sometimes called monoliths, can only be scaled vertically, which is another way of saying that resources must be added to the hardware on which they run in order to increase their capacity to service additional load without hampering latency or throughput. In contrast, modern applications are designed to be scaled horizontally, meaning additional worker instances may be introduced into the resource pool in order to meet the higher demands. This may be handled dynamically, automatically, and without downtime.

Vertical scaling can seldom be performed without introducing downtime, is expensive, and has realistic limits as to the capacity at which a system can scale. Lets take for example a monothically designed service chatbot which has functionalities to interact with a user via a chat interface and perform actions like troubleshooting a complex software system or shifting traffic for said system. The marketing departments of cloud services providers may try to convince developers that their Virtual Machine offerings are easily vertically scalable, which isn't necessarily an outright lie, however scaling the example chatbot on such a VM could prove very expensive, and cannot be done <i>easily</i> without downtime.

Horizontal scaling is the addition of workers to the pool, and is a very popular choice for modern applications which are built around the principle of loose coupling. Platforms like kubernetes and cloudfoundry where applications run in containers sitting behind platform managed load balancers make horizontal scaling as trivial as increasing instance counts of the underlying containers. Though to be fair, they also make vertical scaling as easy as increasing the resource quoatas allocated to each container... with the caveat that typically there's a fairly modest cap to the amount of resources which may be allocated to any one container. Modern platforms and applications are designed around the concept of clustering, and may be horizontally scaled by adding nodes to the cluster. Scaling horezontally is virtually infinate and significantly less cost prohibitive than vertical scaling because it may be acheived by adding modest resources. This may best be conceptualized by thinking of storage as the resource to be scaled, petabyte hard drives may not yet be available and will likely be fairly expensive when first introduced, however petabyte scale storage may currently be acheived through pooling together drives whose capacity is in the terabyte range.

## Availability
In a world where everyone is always connected availability often takes center stage and software system designers must take into account their system availability when going to market. Availability of course is just as it sounds, the inverse of downtime, measured in percentage popularized by the quantity of nines. One 'nine' availability means an uptime of 90 percent, 3 'nines' 99.9 percent, and so forth, driven by Amazon's marketing department which claims 9 'nines' of availability for many of their popular and critical service offerings.

# Service Level Agreement (SLA)
As the label implies, Service Level Agreements, or SLAs for short, are agreements between a servive providers and thier consumers which state explicitly the availability to be provided, and consequences for failing to meet them.

# Mean Time Between Failures (MTBF)
Another benchmark used to measure availability is known as the Mean Time Between Failures. This metric is simply the average or mean time between service outages.

# Busines Impact Analysis (BIA)
A Business Impact Analysis aims to quantify the cost of a service disruption or outage to a business, and may include intangible costs like damage to reputation and trust as well as the very tangible costs of monetary damages resulting from regalatory fines, lost business, lost contracts, and other such impacts.

## Recoverability
Recoverability refers to a system's ability to recover from a service interruption.
# Recovery Time Objective (RTO)
Recovery Time Objective, or RTO is a metric which measures the amount of time required to recover from a service disruption or critical outage, and depending on the complexity and architecture of a system may range from milliseconds to days.
# Recovery Point Objective (RPO)
Recovery Point Objective (RPO) refers to the metric which describes the potential loss of data resulting from a critical outage.

A good architect will design systems such that the RTO and RPO are as close to zero as possible while balancing the cost to create and maintain the system.

## Operability & Maintainability
Operability and Maintainability refer to a system's lifecycle beyond the initial design phase.
# Operability
Operability is the measure of a system's post design and develop lifecycle, from deployment through operation (monitoring, management, reporting) and decomissioning, in terms of effort and cost. The greater the human effort and capital cost to operate a system, the lower its operability rating.
# Maintainability
Maintainability refers to a system's ability to be extended and modified post deployment. If a system cannot be easily extended or modified it is not easiliy maintainable. A good architect will design systems to be highly operable and maintainable.

## Security
Security is a systems ability to protect its own integrity as well as the confidentiality of the data it processes and holds. Security must be considered in all stages of the Software Development Lifecycle from development through operation and decomissioning. A good architect follows best practices to ensure security is woven into the DNA of a system and not circumvented by any individual with access thereto, be they developer, administrator, or end user.

## Sustainability
Sustainability is the minimazation of the impact of a system to the environment and society. AI, crypto, cloud, and other modern novelties can have runaway impacts to energy consumption and privacy which a good architect must mitigate.