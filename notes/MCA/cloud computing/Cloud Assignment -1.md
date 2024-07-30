
### Compute Services

**Compute Service:** These are services that provide processing power in the cloud. Compute services typically involve virtual machines, containers, and serverless functions that allow you to run applications and process data without having to manage physical hardware.
#### Amazon Web Services (AWS)

1. **Amazon EC2 (Elastic Compute Cloud):** Provides resizable compute capacity in the cloud, allowing users to launch virtual servers (instances) on demand, customize configurations, and scale as needed.
2. **AWS Lambda:** A serverless compute service that runs code in response to events and automatically manages the compute resources required by that code.
3. **Amazon ECS (Elastic Container Service):** A container management service that allows you to run and scale containerized applications using Docker.
4. **Amazon EKS (Elastic Kubernetes Service):** A managed Kubernetes service that simplifies running Kubernetes on AWS without needing to install and operate your own control plane.
5. **AWS Fargate:** A serverless compute engine for containers that works with ECS and EKS, eliminating the need to provision and manage servers.
6. **Amazon Lightsail:** A simplified cloud platform that provides everything needed to deploy and manage a virtual private server, including a VM, SSD storage, data transfer, DNS management, and a static IP.

#### Google Cloud Platform (GCP)

1. **Google Compute Engine:** Provides scalable, high-performance virtual machines (VMs) running in Google’s data centers, offering flexible machine types and pricing options.
2. **Google Kubernetes Engine (GKE):** A managed environment for deploying, managing, and scaling containerized applications using Kubernetes.
3. **Google App Engine:** A fully managed platform-as-a-service (PaaS) for building and deploying applications, handling infrastructure concerns like scaling, load balancing, and security.
4. **Google Cloud Functions:** A serverless execution environment for running event-driven code without provisioning or managing servers, triggered by various events.
5. **Google Cloud Run:** A managed compute platform that automatically scales stateless containers, running containers only when needed.

#### Microsoft Azure

1. **Azure Virtual Machines:** Scalable virtual servers providing on-demand compute resources, configurable for different performance requirements.
2. **Azure Kubernetes Service (AKS):** A managed Kubernetes service for deploying, managing, and operating Kubernetes without needing to install or operate your own infrastructure.
3. **Azure App Service:** A fully managed platform for building, deploying, and scaling web apps, supporting multiple languages and frameworks.
4. **Azure Functions:** An event-driven serverless compute service that runs code on demand without managing servers, triggered by events such as HTTP requests, timers, and messages.
5. **Azure Container Instances:** A service to run containers without managing virtual machines or orchestrators, supporting both Linux and Windows containers.

### Storage Services

**Storage Service:** These services provide data storage solutions in the cloud. Storage services include object storage, file storage, and block storage, enabling you to store and retrieve large amounts of data reliably and securely.
#### Amazon Web Services (AWS)

1. **Amazon S3 (Simple Storage Service):** A scalable object storage service designed for data backup, archiving, and analytics, offering high durability and availability.
2. **Amazon EBS (Elastic Block Store):** Provides persistent block storage volumes for use with Amazon EC2 instances, automatically replicated within its Availability Zone.
3. **Amazon EFS (Elastic File System):** A scalable file storage service for use with AWS Cloud services and on-premises resources, supporting the NFS protocol.
4. **Amazon Glacier:** A secure, low-cost cloud storage service for data archiving and long-term backup, with retrieval times ranging from minutes to hours.

#### Google Cloud Platform (GCP)

1. **Google Cloud Storage:** A unified object storage service offering scalability, high durability, and security, with different storage classes for various access needs: Standard, Nearline, Coldline, and Archive.
2. **Persistent Disk:** Durable block storage for virtual machine instances, offering high availability and data redundancy, with SSD and HDD options.
3. **Filestore:** A fully managed file storage service for high-performance workloads, providing a shared file system interface.
4. **Nearline and Coldline Storage:** Low-cost storage options for data archiving and long-term backup, suitable for infrequently accessed data.

#### Microsoft Azure
1. **Azure Blob Storage:** A scalable object storage service optimized for storing massive amounts of unstructured data, such as text or binary data, suitable for data lakes, backups, and archival.
2. **Azure Disk Storage:** High-performance, durable block storage for Azure VMs, supporting SSD and HDD disk types, with features like shared disks and encryption.
3. **Azure Files:** Fully managed file shares in the cloud accessible via the SMB protocol, allowing the replacement or supplementation of on-premises file servers.
4. **Azure Archive Storage:** A cost-effective solution for long-term data storage and archiving, providing low-cost storage for rarely accessed data with retrieval options ranging from minutes to hours.

### Database Services

**Database Service:** These are managed services for storing, managing, and retrieving data. Database services can be relational (SQL) or non-relational (NoSQL), and they provide features like scalability, high availability, backup, and recovery.

#### Amazon Web Services (AWS)

1. **Amazon RDS (Relational Database Service):** Simplifies setting up, operating, and scaling a relational database in the cloud, supporting several database engines including Aurora, PostgreSQL, MySQL, MariaDB, Oracle, and SQL Server.
2. **Amazon DynamoDB:** A fast and flexible NoSQL database service designed for single-digit millisecond performance at any scale, offering built-in security, backup and restore, and in-memory caching.
3. **Amazon Redshift:** A fast, fully managed data warehouse service that makes it simple and cost-effective to analyze all your data using SQL and existing business intelligence tools.
4. **Amazon Aurora:** A MySQL and PostgreSQL-compatible relational database built for the cloud, combining high performance and availability with cost-effectiveness.
5. **Amazon DocumentDB:** A scalable, fully managed document database service that supports MongoDB workloads, designed for high availability and durability.
6. **Amazon Neptune:** A fully managed graph database service designed to build and run applications that work with highly connected datasets.

#### Google Cloud Platform (GCP)

1. **Google Cloud SQL:** A fully managed relational database service supporting MySQL, PostgreSQL, and SQL Server, automating backups, replication, and failover.
2. **Google Cloud Spanner:** A globally distributed, horizontally scalable relational database service designed for mission-critical applications, offering strong consistency and high availability.
3. **Google Bigtable:** A fully managed, scalable NoSQL database service for large analytical and operational workloads, providing low-latency data access.
4. **Google Firestore:** A NoSQL document database built for automatic scaling, high performance, and ease of application development, supporting real-time synchronization.
5. **Google BigQuery:** A fully managed, serverless data warehouse for fast SQL queries using the processing power of Google’s infrastructure, designed for analyzing large datasets quickly and easily.

#### Microsoft Azure

1. **Azure SQL Database:** A fully managed relational database service offering built-in intelligence, scalability, and high availability, with multiple deployment options including single databases, managed instances, and elastic pools.
2. **Azure Cosmos DB:** A globally distributed, multi-model database service providing low-latency data access and high availability, supporting key-value, document, column-family, and graph data models.
3. **Azure Database for MySQL:** A fully managed MySQL database service offering high availability, automated backups, and scaling.
4. **Azure Database for PostgreSQL:** A fully managed PostgreSQL database service providing high availability, scaling, and automated backups.
5. **Azure Database for MariaDB:** A fully managed MariaDB database service with high availability, scaling, and automated backups.
6. **Azure Synapse Analytics:** An analytics service combining big data and data warehousing, offering a unified experience to ingest, prepare, manage, and serve data for immediate business intelligence and machine learning needs.

