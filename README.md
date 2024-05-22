# AWS Static S3 Project - Aprió

## About The Project 

- This project was developed to showcase my understanding of cloud architecture and the fundamentals of constructing IT infrastructure on Amazon Web Services (AWS).
- It highlights my knowledge of the six pillars of the AWS Well-Architected Framework. 
- It also illustrates my understanding of various design patterns, aiding me in architecting IT solutions on AWS.
- I have created a very basic restaurant website, which I will be basing this project around

### Part One:

#### 1.1:

- Aprió which is a basic static site consisting on an HTML, CSS and image files has been uploaded to Amazon S3.
- As it is intended to be a publicly accessible site - public access was granted
- A bucket policy was then created to grant public read access
  
#### 1.2:
  
- To protect the website data and implement architecture best practices, bucket versioning is enabled.
- To optimize storage costs and implement architecture best practices I have implemented lifecycle policies. The reason for this is now that bucket versioning is enabled, although it is free each version is a copy of an object in my bucket and therefore adds to storage costs.
- The first policy moves non-current versions into the S3 Standard Infrequent Access (IA) storage class after 30 days.
- The second policy deletes non-current versions after 90 days.

#### 1.3:

- For enhanced durability and disaster recovery planning I have enabled Cross-Region replication. This is another architecture best practice which is automating disaster recovery
- I have created a replication rule that has replicated my bucket into another bucket in another region and will replicate any future versions of objects I upload into my source bucket.