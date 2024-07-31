# Correction du Questionnaire sur AWS (Amazon Web Services)

## Questions à choix unique (en français)

1. Quel service AWS fournit des serveurs virtuels dans le cloud ?
   
   Réponse correcte : b) EC2
   
   Explication : EC2 (Elastic Compute Cloud) est le service d'AWS qui fournit des serveurs virtuels dans le cloud. Il permet aux utilisateurs de louer des machines virtuelles sur lesquelles ils peuvent exécuter leurs propres applications.

2. Quel service AWS est utilisé pour la gestion des accès et des identités ?
   
   Réponse correcte : c) IAM
   
   Explication : IAM (Identity and Access Management) est le service d'AWS utilisé pour gérer de manière sécurisée l'accès aux services et ressources AWS. Il permet de créer et gérer des utilisateurs, des groupes et des rôles, ainsi que de définir des permissions fines.

## Questions ouvertes (en anglais)

1. Explain the concept of "Regions" and "Availability Zones" in AWS. Why are they important for building resilient applications?

   Réponse modèle : 
   In AWS:
   - Regions are separate geographic areas where AWS clusters data centers. Each region is completely independent and isolated from other regions.
   - Availability Zones (AZs) are multiple, isolated locations within each region. Each AZ has independent power, cooling, and networking infrastructure.

   Importance for building resilient applications:
   1. High Availability: By distributing applications across multiple AZs within a region, you can ensure that your application remains available even if one AZ fails.
   2. Disaster Recovery: Regions allow for geographic redundancy. You can replicate data and resources across regions to protect against large-scale disasters.
   3. Low Latency: By choosing a region close to your users, you can reduce latency and improve application performance.
   4. Data Sovereignty: Regions allow you to keep data within specific geographic boundaries to comply with data residency requirements.
   5. Scalability: Different regions may offer different services or instance types, allowing you to scale your application using the most appropriate resources.

   By leveraging Regions and AZs effectively, you can design applications that are highly available, fault-tolerant, and capable of surviving various types of failures or disasters.

2. What is the difference between Amazon EBS and Amazon S3? In what scenarios would you use each?

   Réponse modèle:
   Amazon EBS (Elastic Block Store) and Amazon S3 (Simple Storage Service) are both storage services, but they serve different purposes:

   Amazon EBS:
   - Block-level storage volumes for EC2 instances
   - Behaves like a physical hard drive
   - Provides low-latency access
   - Data persists independently from the life of an instance
   - Can only be attached to one EC2 instance at a time (in most cases)

   Amazon S3:
   - Object storage service
   - Highly scalable and durable
   - Accessed via HTTP/S
   - Can store virtually unlimited amounts of data
   - Objects can be accessed from anywhere on the web

   Scenarios for EBS:
   1. Running databases on EC2 instances
   2. Boot volumes for EC2 instances
   3. Applications that require file system access and block storage
   4. Scenarios requiring frequent read/write operations

   Scenarios for S3:
   1. Storing and distributing static web content and media
   2. Data backup and archiving
   3. Hosting entire static websites
   4. Big data analytics
   5. Content delivery in conjunction with CloudFront

   In summary, use EBS when you need high-performance, block-level storage for EC2 instances, and use S3 when you need highly scalable, durable object storage that can be accessed from anywhere on the web.

