# Cloud Native Workshop
Primary repository for Cloud Native Development workshop.

## Description
Want to learn Cloud Native Development from concept to execution but don't know where to start? Need to sink your hands into it under expert tutelage? This workshop is for you.

In this guided lab, we will start by explaining the following key concepts:

* The Evolution of Cloud Native Development
* 12 (or so) Factor Apps: A Starting Point
* Microservices Architectures: A Smart Fit

Once you understand the foundational concepts, it's time to put that knowledge to use. We'll help you build your Cloud Native knowledge & practical experience as you:

* Create a self-contained, cloud-executable Java application
* Create a code repository for your program
* Configure your application's environment for portability
* Connect to backing services as resources (microservices)
* Make it stateless, "share nothing" for scalability and reliability (microservices)
* Create and expose an endpoint, making your app a backing (micro)service
* Deploy to the cloud, then test disposability/robustness
* Examine monitoring and logging capabilities

Each exercise performed will be shown in context so attendees learn and internalize the why _and_ how of Cloud Native development practices.

## Additional Notes/Excess Material

* (_MENTION, BUT SKIP FOR INTRO WORKSHOP_) Create build/release/run pipeline
* (_MENTION, BUT SKIP FOR INTRO WORKSHOP_) Create horizontally scalable configuration (NOTE: This would require service directory, circuit breaker, load balancer...)
* (_MENTION, BUT SKIP FOR INTRO WORKSHOP_) Dev/prod parity (NOTE: Out of scope for this workshop)
* (_MENTION, BUT SKIP FOR INTRO WORKSHOP_) Incorporate admin code into release for consistency

## Outline

In this workshop, we will start by explaining the following key concepts:

* The Evolution of Cloud Native Development
* 12 (or so) Factor Apps: A Starting Point
* Microservices Architectures: A Smart Fit

Once you understand the foundational concepts, it's time to put that knowledge to use. We'll help you build your Cloud Native knowledge & practical experience as you:

* Create a self-contained, cloud-executable Java application
  * Simple app that includes the HAL Browser, dependencies for HATEOAS, REST Repositories, JPA, H2 (use initially, switch to MySQL CF backing service), ???
* Create a code repository for your program
* Configure your application's environment for portability
  * Port number? (locally)
  * Backing service as env var
  * Default quote?
* Deploy to the cloud (new)
* Connect to backing services as resources (microservices)
  * "Convert" from H2 to MySQL (create service)
  * Add spring.jpa.generate-ddl=true to application.properties
  * cf push
  * Verify contents of MySQL db using CLI
    * cf env <appname>, check under "cleardb" in "VCAP_SERVICES"
    * mysql -u <username> -p<password> --host <hostname>
* Make it stateless, "share nothing" for scalability and reliability (microservices)
  * Discuss shared persistent data (MySQL backing service)
  * cf scale <appname> -i 3
  * What else to mention?
* Create and expose an endpoint, making your app a backing (micro)service
  * Create /random
  * cf push
  * Test
* Deploy to the cloud, then test disposability/robustness
  * cf env <appname> _or_
  * cf curl -X GET "/v2/apps"
  * cf curl "/v2/apps/<application_id/guid>/instances/1" -X DELETE
  * cf app <appname>
* Examine monitoring and logging capabilities

## Prerequisites

* Git installed
  * https://git-scm.com/downloads
  * Or via homebrew (Mac) or your favorite package manager (Linux)
* Github or Gitlab or BitBucket account
  * https://github.com/
  * https://about.gitlab.com/
  * https://bitbucket.org/
* MySQL CLI installed (optional, but helpful for verification)
  *  https://dev.mysql.com/downloads/
  * Or via homebrew (Mac) or your favorite package manager (Linux)
* IntelliJ IDEA or NetBeans or STS installed: choose one, please
  * https://www.jetbrains.com/idea/download/
  * https://netbeans.org/downloads/index.html (choose "Java EE" or "All" version)
  * https://spring.io/tools
* Maven installed
  * https://maven.apache.org/download.cgi
  * Or via homebrew (Mac) or your favorite package manager (Linux)
* Cloud Foundry account: Sign up in advance by visiting https://run.pivotal.io and choosing "free trial". If unable to create a free trial, please email support@run.pivotal.io for assistance.
* Cloud Foundry Command Line Interface (CLI)
  * https://console.run.pivotal.io/tools (accessed from the console once free trial is created)

## Completed project repo

* https://github.com/hecklerm/cnworkshop
