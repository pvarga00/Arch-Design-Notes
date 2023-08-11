# Arch-Design-Notes
Personal notes on Arch Design & Patterns
[Original source: "Migrating to CLoud-Native Application Architectures" by Matt Stine (O'Reilly)]

# Cloud Native Application Architectures & Considerations
## Speed:
Speed wins in the marketplace, NLS, city and self-service. Nature of cloud based infrastructure naturally lends itself to this way of working.

## Safety:
### Visibility & Fault Isolation/Tolerance
- Visibility must identify components contributing to the deviations. Feature rich metrics monitoring, alerting and data visualization frameworks. Are needed for all cloud native architectures.
- Fault Isolation. Composable systems for microservices are especially important. Especially for. Independently deployable components preventing failures from cascading.
- Circuit Breaker Pattern. Graceful falilovers & Automated recovery
  - This is great to have especially. Extended health checks. To answer whether a service is healthy, unhealthy, up or down. With failed health checks, we simply often restart or redeploy the service.
- Cloud native application architectures cannot wait for manual intervention. We need to employ automated detection and recovery.

## Scale:
- Horizontal instead of vertical scaling. Decomposing monoliths. Externalization of end state and in memory data grids, caches, and persistent object stores. Stateless applications can quickly be created and destroyed, as well as attached to and detached from external state managers. External state managers themselves must also be scalable.

# 12 Factor Applications:
- Is a collection of patterns for cloud native application architectures.
- 12 factor apps can be defined by:
  -  A code base.
  -  Dependencies.
  -  Config.
  -  Backing services.
  -  Build, Release, run.
  - Processes.
  - Port bindings.
  - Concurrency.
  - Disposability.
  - Dev/Prod Parity.
  - Logs.
  - Admin processes.

- Microservices represent the decomposition of monolithic business systems into independently deployable services. Following the single responsibility or do one thing Well pattern. Usually it represents a business capability or a unit that is atomic that delivers business value.

- Self-service Agile infrastructure. Primary abstraction layer for consumers, often also called Infrastructure as a Service or IAS. API's create virtual server instances, networks and storage and then applied various forms of config management and automation to enable applications and supporting services to run. Application code is simply pushed in the form of prebuilt artifacts. Docker. K Eights and rancher. Will help with this. Service instances should be bound to an application with necessary credentials automatically injected at runtime into an applications environment. Automated and on demand scaling of application instances, application health management, dynamic routing and load balancing of requests. Aggregation of logs and metrics.

- API based collaboration. API should typically be HTTP REST style with JSON serialization, but I can also use other protocols in serialization formats. Contract compliance can be verified on both sides of a service to service interaction via consumer driven contracts. Service consumers are not allowed to gain access to private implementation details of their dependencies or direct access to their dependencies data stores. Force decoupling directly supports cloud native goal of speed and scalability.

- Antifragility. Is the quality of a system that self-heals or fixes itself, when subjected to stressors.
  - Adopters of cloud native architectures seek to find faults such as Chaos Monkey, which injects random failures into Production components with the goal of identifying and eliminating weaknesses in architectures and applications. By seeking out weaknesses in the application architecture, injecting failures, and forcing their remediation, architectures naturally converge on a greater degree of safety over time practicing typical faults.

- Centralized governance versus decentralized autonomy.

- Water Scrum fall culture merits special mention. It's a real sticking point in cloud native adoption.

- Centralized governance structures around application architecture and data management, with committees responsible for maintaining guidelines and standards as well as improving. And approving individual designs and changes. These standards. Can help prevent widespread inconsistency in technology stacks, decreasing the overall maintenance burdens for the organization. They can also prevent widespread inconsistencies in architectural choices, allowing for a common view of application development across an organization. Cross-cutting concerns like regulatory compliance. Can be handled in a consistent way for the entire organization. And ownership of data can be determined by those who have a broad view of all organizational concerns, including lineage. ETL's data transformations and storage, including. Encryption at rest and in transit.


![AWS Arch Diagram](https://github.com/pvarga00/Arch-Design-Notes/blob/main/Default%20AWS%20Arch%20Template.drawio.svg)
![PartCatalog ArchDiag](https://github.com/pvarga00/Arch-Design-Notes/blob/main/Sample%20Parts%20Catalog.svg)
![AWS EC2 ArchDiag](https://github.com/pvarga00/Arch-Design-Notes/blob/main/ec2-basic-arch.png)
