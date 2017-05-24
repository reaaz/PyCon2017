# Python in the Serverless Era by Benny Bauer
## What is serverless
### Dev SaaS
* Auth0
* Twilio
* Cloudinary
* Algorthmia
### BaaS (backend as a service)
* Firebase
### FaaS (function as a service)
* AWS Lambda
* Azure functions
* Google cloud functions
## What is FaaS?
* Fully-managed compute - provisioning, patching, scaling, monitoring, logging provided out of the box
* Deploy your code
* Pay for actual usage - charged only upon code execution per 100ms [no idle compute]
## How it works
1. Deploy your code
2. Define triggers [event-driven] (http requests, storage [file upload], scheduled tasks, messaging, db row insert, etc)
3. Code execution (auto scaling + availability)
## Use cases
* API - web or mobile or bot
* Operations - CI, policy enforcement, provisioning
* Data processing - IoT, streams (analytics)
* Other - scheduled tasks
## Things to be aware of
* Stateless
* Cold start
* Vendor lock-in
* Costs
* Granularity
* Limitations
## Cloud Providers
* Python 2.7 and 3.6 supported by AWS, OpenWhisk, and Azure
## Need for frameworks
* Configuration
* Deployment
## Frameworks
### Serverless
* Most mature
### Zappa
* One function only, serves as a WSGI server (so you can use django or flask)
* Really easy
* global deployment (to all AWS regions)
* "Keep warm" functionality
* SSL certs
* Support for AWS lambda compatible python libraries (lambda-packages & manylinux wheels - python precompiled lambda packages)
### Chalice - define it in your code and deploy
### Pywren - take a function from your code and distribute it to a number of lambas at run-time [really good for a scraper]
### Apdex
### Takeaways
* Fast to develop, cost-effective for many use cases
* New frontiers for Python (frameworks, tooling, etc.)
