# S3 
## intro
S3 instances hold data, the data can then later be accessed via url,

we can upload and create s3 from the awscli comand library package

this package allows us to create and change buckets that hold the data.

any image or text file or other data can then be accessed from the URl of the bucket and a specified url
![cat](image.png)
![Alt text](image-1.png)

we see that the picture can be changed
this is done in the steps

## Steps
1. deploying the app
2. creating and using bucket image
3. reverting

each step is a script that can be run, and running either one of the latter 2 will change the image back and forth

## the code for all 3 is here:
### code was removed for safety purposes
[1](Voorhees.sh)
[2](prov.sh)
[3](remove_bucket.sh)

## S3 research
### Data Replication and Durability:

#### Multiple Availability Zones (AZs): S3 allows you to store data in multiple Availability Zones. AWS operates multiple data centers in different geographical locations called Availability Zones. Storing data in multiple AZs ensures that your data is replicated across different physical locations, providing durability and fault tolerance.

#### Data Durability: S3 provides 99.999999999% (11 nines) durability for objects stored in the service. This level of durability is achieved through redundant storage of objects across multiple devices and facilities.

### Redundancy Options:

#### Standard Storage Class: S3's standard storage class replicates data across multiple devices within an AZ and may also replicate data across multiple AZs. It is suitable for frequently accessed data where low-latency access is important.

#### Reduced Redundancy Storage (RRS): Although not recommended for critical data, RRS provides a cost-effective storage option by replicating objects across multiple devices in a single AZ. It offers a lower level of durability (99.99%) compared to the standard storage class.

#### One Zone-Infrequent Access (IA): This storage class stores data in a single AZ, making it less expensive than standard storage. However, it is not as fault-tolerant as the standard storage class, as it doesn't replicate data across multiple AZs.

#### Glacier: S3 Glacier is designed for long-term archival and provides further cost savings. It allows you to archive data with different retrieval options.

### Versioning:

##### S3 supports versioning, which means multiple versions of an object can be stored. This feature helps in recovering from accidental deletions or overwrites.
### Cross-Region Replication (CRR):

##### S3 offers Cross-Region Replication, allowing you to replicate objects across different AWS regions. This is useful for disaster recovery scenarios where data needs to be available in a different geographic location in case of a regional outage.
#### Lifecycle Policies:

##### S3 provides lifecycle policies that automate the transition of objects between storage classes or even the expiration of objects after a certain period. This helps in managing costs and ensuring that data is stored appropriately based on its access patterns.
#### Event Notifications:

##### S3 allows you to set up event notifications based on specific events (e.g., object creation, deletion). This can be used to trigger automated workflows or notifications for disaster recovery scenarios