---

copyright:
  years: 2026
lastupdated: "2026-04-21"

keywords: sandbox best practices, vpc best practices, cloud sandbox optimization, sandbox security, resource management

subcollection: sandbox

---

{{site.data.keyword.attribute-definition-list}}

# Best practices for IBM Cloud Sandbox
{: #sandbox-best-practices}

This document provides recommended best practices for effectively using the IBM Cloud Sandbox environment. Following these guidelines helps you maximize the value of your 14-day trial period, optimize resource usage, and gain meaningful insights for your cloud migration or evaluation journey.
{: shortdesc}

## Planning and preparation
{: #planning-preparation}

Proper planning before creating your sandbox environment ensures you make the most of your trial period.

### Define clear objectives
{: #define-objectives}

Before requesting sandbox access, establish specific goals for your evaluation:

* Identify the workloads or applications you want to test
* List the IBM Cloud services and features you need to evaluate
* Define success criteria for your evaluation (performance benchmarks, feature validation, migration readiness)
* Create a timeline for testing activities within the 14-day period
* Document any compliance or security requirements that need validation

Having clear objectives helps you focus your efforts and ensures you gather the information needed to make informed decisions.
{: tip}

### Assemble your team early
{: #assemble-team}

Collaboration is more effective when team members are involved from the start:

* Identify all stakeholders who should participate in the evaluation
* Add team members during sandbox creation rather than inviting them later
* Assign appropriate permission levels based on each member's role:
  - **Administrators** for team leads who need full control
  - **Editors** for developers and engineers who will create and modify resources
  - **Viewers** for stakeholders who need visibility without making changes
* Schedule kickoff meetings to align on objectives and responsibilities
* Establish communication channels for sharing findings and coordinating activities

### Document your current environment
{: #document-environment}

Understanding your existing infrastructure helps you design effective tests:

* Document current workload specifications (CPU, memory, storage, network requirements)
* List dependencies between applications and services
* Identify performance baselines and SLAs from your current environment
* Note any custom configurations or integrations that need testing
* Capture security and compliance requirements that must be maintained

This documentation serves as a reference point for comparing sandbox performance and capabilities.

## Resource management
{: #resource-management}

Efficient resource management ensures you can test all necessary scenarios within sandbox limits.

### Start with minimal configurations
{: #minimal-configs}

Begin with smaller resource allocations and scale up as needed:

* Start with balanced compute profiles before testing specialized profiles
* Use smaller storage volumes initially and expand based on actual requirements
* Deploy one or two server instances first to validate configurations
* Test basic networking before implementing complex architectures
* This approach conserves resources and allows for iterative testing

You can always provision additional resources or upgrade configurations as you progress through your evaluation.
{: note}

### Prioritize critical workloads
{: #prioritize-workloads}

Focus on your most important use cases first:

* Test mission-critical applications before secondary workloads
* Validate core functionality before exploring advanced features
* Ensure essential integrations work before testing optional components
* Document results for priority items before moving to lower-priority tests
* Leave buffer time for unexpected issues or additional testing needs

### Monitor resource consumption
{: #monitor-consumption}

Regularly check your resource usage to avoid hitting limits:

* Review active resources in the IBM Cloud Console daily
* Track the number of running instances, storage volumes, and network resources
* Identify and delete unused or idle resources promptly
* Monitor storage consumption and clean up unnecessary data
* Keep notes on which resources are essential for ongoing tests

Proactive monitoring prevents resource exhaustion and ensures you can complete all planned testing activities.

## Server provisioning best practices
{: #server-provisioning}

Follow these guidelines when creating Virtual Server Instances or Bare Metal Servers.

### Choose the right server type
{: #choose-server-type}

Select the appropriate server type based on your workload characteristics:

* **Use Virtual Server Instances (VSI) for:**
  - Development and testing environments
  - Web applications and microservices
  - Workloads with variable resource demands
  - Quick deployment and iteration cycles
  - Most evaluation and learning scenarios

* **Use Bare Metal Servers for:**
  - High-performance computing requirements
  - Database servers with intensive I/O operations
  - Applications requiring consistent, dedicated resources
  - Workloads with strict compliance or isolation requirements
  - Performance benchmarking against physical infrastructure

VSIs are recommended for most sandbox users due to faster provisioning times and greater flexibility.
{: tip}

### Select appropriate compute profiles
{: #select-compute-profiles}

Match compute profiles to your workload requirements:

* **Balanced profiles** - Start here for general-purpose applications and unknown workload patterns
* **Compute-optimized profiles** - Use for CPU-intensive tasks like batch processing, scientific computing, or video encoding
* **Memory-optimized profiles** - Choose for databases, caching systems, in-memory analytics, or data processing applications

Test with profiles that match your production workload characteristics to get accurate performance insights.

### Configure networking thoughtfully
{: #configure-networking}

Plan your network configuration based on security and accessibility needs:

* Use **private networks** for backend services, databases, and internal applications
* Enable **public networks** only for web-facing applications or services requiring internet access
* Configure security groups and firewall rules to restrict traffic to necessary ports and protocols
* Test VPN connectivity early if you need secure access to private resources
* Document network configurations for replication in production environments

### Plan storage allocation
{: #plan-storage}

Optimize storage configuration for performance and capacity:

* Allocate sufficient boot volume size for your operating system and applications
* Add separate data volumes for databases, logs, and user data
* Choose SSD storage for performance-critical applications
* Use HDD storage for capacity-focused workloads with lower I/O requirements
* Plan for data growth during your testing period
* Regularly clean up unnecessary files and logs to conserve storage

## Security best practices
{: #security-practices}

Maintain security best practices even in a trial environment.

### Implement access controls
{: #access-controls}

Manage user access and permissions carefully:

* Follow the principle of least privilege when assigning user permissions
* Regularly review the list of collaborators and remove access for users who no longer need it
* Use strong, unique passwords for all server instances and services
* Enable multi-factor authentication (MFA) for your IBM Cloud account
* Avoid sharing credentials between team members

### Secure your servers
{: #secure-servers}

Apply security measures to all provisioned servers:

* Keep operating systems and software up to date with security patches
* Configure firewalls to allow only necessary inbound and outbound traffic
* Disable unused services and ports on server instances
* Use SSH keys instead of passwords for Linux server authentication
* Implement network segmentation to isolate different application tiers
* Enable logging and monitoring to detect unusual activity

### Protect sensitive data
{: #protect-data}

Handle data responsibly in the sandbox environment:

* Avoid using production data or personally identifiable information (PII) in the sandbox
* Use synthetic or anonymized data for testing purposes
* Encrypt sensitive data at rest and in transit
* Implement proper data retention and deletion policies
* Remember that all data will be permanently deleted when the trial period ends

Do not store sensitive production data or customer information in the sandbox environment.
{: important}

## Collaboration best practices
{: #collaboration-practices}

Effective collaboration maximizes team productivity and learning.

### Establish clear communication
{: #clear-communication}

Set up communication channels and protocols:

* Create a dedicated Slack channel, Teams group, or email thread for sandbox-related discussions
* Schedule regular sync meetings to share progress and findings
* Document decisions, configurations, and test results in a shared location
* Use descriptive naming conventions for resources to indicate ownership and purpose
* Communicate planned activities that might affect other team members' work

### Coordinate resource usage
{: #coordinate-resources}

Prevent conflicts and resource contention:

* Assign specific resources or workloads to individual team members
* Communicate before making changes to shared resources
* Use tags to identify resource ownership and purpose
* Avoid deleting or modifying resources created by other team members without coordination
* Establish a process for requesting and approving resource-intensive activities

### Share knowledge and findings
{: #share-knowledge}

Maximize learning across the team:

* Document configurations, procedures, and test results as you work
* Share successful configurations and workarounds with team members
* Conduct knowledge-sharing sessions to discuss findings and insights
* Create runbooks or guides for common tasks and configurations
* Capture lessons learned for future reference and production implementation

## Testing and evaluation strategies
{: #testing-strategies}

Structured testing approaches yield more valuable insights.

### Create realistic test scenarios
{: #realistic-scenarios}

Design tests that reflect actual use cases:

* Replicate production workload patterns and traffic volumes
* Test peak load scenarios and stress conditions
* Validate failover and disaster recovery procedures
* Simulate user interactions and application workflows
* Include integration testing with dependent services

### Measure and document performance
{: #measure-performance}

Collect quantitative data to support decision-making:

* Establish performance baselines before making changes
* Measure response times, throughput, and resource utilization
* Compare sandbox performance against current infrastructure
* Document any performance bottlenecks or limitations encountered
* Capture metrics that align with your success criteria

### Test migration scenarios
{: #test-migration}

If planning a migration, validate the migration process:

* Test data migration procedures and tools
* Validate application compatibility with VPC infrastructure
* Identify any code changes or configuration adjustments needed
* Test rollback procedures in case of issues
* Document the migration process for production implementation

### Validate integrations
{: #validate-integrations}

Ensure all necessary integrations function correctly:

* Test connections to external services and APIs
* Validate authentication and authorization mechanisms
* Test data synchronization and replication processes
* Verify monitoring and logging integrations
* Confirm backup and disaster recovery procedures

## Time management
{: #time-management}

Maximize the value of your 14-day trial period.

### Create a testing schedule
{: #testing-schedule}

Plan your activities across the trial period:

* **Days 1-2**: Environment setup, initial configuration, and team onboarding
* **Days 3-7**: Core functionality testing and primary workload evaluation
* **Days 8-11**: Advanced features, integration testing, and performance benchmarking
* **Days 12-13**: Documentation, knowledge transfer, and final validation
* **Day 14**: Data export, final documentation, and environment cleanup preparation

Adjust this schedule based on your specific objectives and team size.

### Build in buffer time
{: #buffer-time}

Account for unexpected challenges:

* Reserve time for troubleshooting and problem resolution
* Allow flexibility for exploring unexpected findings or opportunities
* Plan for learning curves with new services or features
* Schedule time for team discussions and decision-making
* Keep the final day available for wrap-up activities

### Request extensions strategically
{: #request-extensions}

If you need more time, plan your extension request:

* Request extensions before your trial period expires
* Provide clear justification for the additional time needed
* Specify exactly what you plan to accomplish during the extension
* Remember that extensions are limited to 2 days and are not guaranteed
* Use extension time for critical activities that couldn't be completed

## Documentation and knowledge capture
{: #documentation}

Thorough documentation ensures you retain value from your sandbox experience.

### Document configurations
{: #document-configs}

Record all important configuration details:

* Server specifications (compute profiles, operating systems, storage)
* Network configurations (VPCs, subnets, security groups, firewall rules)
* Service configurations (Load Balancer, VPN, Transit Gateway, Cloud Object Storage)
* Integration settings and connection details
* Custom scripts, automation, or infrastructure-as-code templates

### Capture test results
{: #capture-results}

Record findings from your testing activities:

* Performance metrics and benchmarks
* Successful configurations and best practices discovered
* Issues encountered and their resolutions
* Comparison with current infrastructure or alternative solutions
* Recommendations for production implementation

### Create implementation guides
{: #implementation-guides}

Prepare for production deployment:

* Document step-by-step procedures for recreating successful configurations
* List prerequisites and dependencies for production deployment
* Identify differences between sandbox and production requirements
* Create checklists for migration or deployment activities
* Note any lessons learned or pitfalls to avoid

### Export important data
{: #export-data}

Save critical information before the trial ends:

* Export configuration files and scripts
* Download test data, logs, and results
* Save screenshots of important configurations or dashboards
* Export monitoring data and performance metrics
* Back up any code or applications developed during testing

All sandbox resources are permanently deleted when the trial period ends. Export any important data before expiration.
{: important}

## Cost optimization for production
{: #cost-optimization}

Use sandbox insights to optimize future costs.

### Identify right-sizing opportunities
{: #right-sizing}

Determine optimal resource allocations:

* Note which compute profiles provided adequate performance
* Identify over-provisioned resources that could be downsized
* Document minimum resource requirements for each workload
* Test auto-scaling configurations to optimize resource usage
* Compare costs of different configuration options

### Evaluate service alternatives
{: #service-alternatives}

Assess different service options and tiers:

* Test multiple storage types to find the best cost-performance balance
* Compare different Load Balancer configurations
* Evaluate whether all automatically provisioned services are necessary
* Identify opportunities to consolidate services or resources
* Document cost implications of different architectural choices

### Plan for production efficiency
{: #production-efficiency}

Apply sandbox learnings to production planning:

* Use sandbox findings to create accurate cost estimates for production
* Identify opportunities for reserved capacity or committed use discounts
* Plan resource allocation strategies based on actual usage patterns
* Document cost optimization opportunities discovered during testing
* Create a cost monitoring and optimization plan for production

## Migration preparation
{: #migration-preparation}

If planning to migrate from Classic infrastructure, use the sandbox to prepare.

### Validate workload compatibility
{: #validate-compatibility}

Ensure your applications work in VPC environments:

* Test application functionality in VPC infrastructure
* Identify any compatibility issues or required code changes
* Validate performance meets or exceeds current environment
* Test all integrations and dependencies
* Document any modifications needed for VPC deployment

### Develop migration procedures
{: #migration-procedures}

Create detailed migration plans:

* Document the migration process step-by-step
* Identify migration tools and utilities needed
* Plan for data migration and synchronization
* Develop rollback procedures for each migration phase
* Create testing and validation checklists

### Train your team
{: #train-team}

Prepare your team for VPC operations:

* Ensure team members understand VPC concepts and terminology
* Provide hands-on experience with VPC management tools
* Document operational procedures for VPC environments
* Identify training needs for production operations
* Create knowledge base articles and runbooks

## Troubleshooting and support
{: #troubleshooting-support}

Effective problem-solving maximizes your sandbox productivity.

### Leverage available resources
{: #leverage-resources}

Use IBM Cloud documentation and support:

* Consult IBM Cloud documentation for service-specific guidance
* Review tutorials and how-to guides for common tasks
* Check the FAQ section for answers to common questions
* Use IBM Cloud support channels for technical assistance
* Participate in IBM Cloud community forums and discussions

### Document issues and resolutions
{: #document-issues}

Keep track of problems and solutions:

* Record all issues encountered during testing
* Document troubleshooting steps and resolutions
* Share solutions with team members to prevent duplicate efforts
* Note any workarounds or limitations discovered
* Report bugs or documentation gaps to IBM Cloud support

### Escalate appropriately
{: #escalate-appropriately}

Know when to seek additional help:

* Contact IBM Cloud support for technical issues beyond your expertise
* Request assistance if you encounter service outages or critical problems
* Ask for guidance on complex configurations or best practices
* Seek clarification on service limitations or capabilities
* Request trial extensions if needed to complete critical testing

## Post-sandbox actions
{: #post-sandbox}

Complete these activities before and after your trial ends.

### Export all critical information
{: #export-information}

Save everything you need before the trial expires:

* Export all configuration files, scripts, and code
* Download test results, logs, and performance data
* Save documentation, diagrams, and architecture designs
* Back up any data or applications created during testing
* Capture screenshots of important configurations

### Conduct a retrospective
{: #conduct-retrospective}

Review your sandbox experience with your team:

* Discuss what worked well and what could be improved
* Review whether you achieved your evaluation objectives
* Identify gaps in testing or areas needing further investigation
* Capture lessons learned for future cloud initiatives
* Make go/no-go decisions based on sandbox findings

### Plan next steps
{: #plan-next-steps}

Determine your path forward:

* Decide whether to proceed with VPC adoption or migration
* Create a detailed implementation plan for production deployment
* Identify additional resources or training needed
* Establish timelines for production implementation
* Assign responsibilities for next-phase activities

### Provide feedback
{: #provide-feedback}

Help improve the sandbox experience:

* Share feedback about the sandbox environment with IBM Cloud
* Suggest improvements or additional features
* Report any issues or limitations encountered
* Recommend documentation enhancements
* Share success stories or use cases

## Summary
{: #summary}

Following these best practices helps you maximize the value of your IBM Cloud Sandbox experience. Key takeaways include:

* Plan thoroughly before creating your sandbox environment
* Manage resources efficiently to complete all testing objectives
* Implement security best practices even in trial environments
* Collaborate effectively with your team
* Document everything for future reference
* Use sandbox insights to optimize production deployments
* Export critical information before the trial period ends

By applying these guidelines, you'll gain meaningful insights into IBM Cloud VPC capabilities and be well-prepared for successful production implementation or migration.

## Related information
{: #related-information}

* [Getting started with IBM Cloud Sandbox](/docs/sandbox?topic=sandbox-getting-started-sandbox)
* [About IBM Cloud Sandbox](/docs/sandbox?topic=sandbox-architecture)
* [Deploying the Sandbox](/docs/sandbox?topic=sandbox-deploy)
* [FAQs](/docs/sandbox?topic=sandbox-my-service-faq)
* [Troubleshooting](/docs/sandbox?topic=sandbox-troubleshoot)
