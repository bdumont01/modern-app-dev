# Overall Guidance

This git repo has been created as part of a larger overall framework that will allow less technical users to demonstrate the business value of our products.  The framework consists of three artifacts:

1) A Miro Board that specifies:
   * Business Value Statement
   * A Specific Scenario that should be addressed
   * The IT Value that should be demonstrated by this demo
   * This link provides a sample output of this activity
2) An Asana Task List that provides step-by-step details on the process that the account team should go through prior to embarking on the demo
  * A link to the template is provided here
  * This task list has been templatized and will allow an account team to walk through the process that will lead to the type of demo that needs to be created 
3) A Simplified Demo that shows the business value of Red Hat products.
  * Demo 1 has been created to show the results of this process and can be used as is

# Technical Approach

When this demonstration is provisioned it will create the environment based on the Red Hat Modern Application Development Workshop.  

Therefore the base infrastructure will be deployed with:

  * Openshift Container Platform
  * Red Hat OpenShift Pipelines Operator 
  * Red Hat OpenShift GitOps Operator 

Additionally the infrastructure will deploy with development tools that will be used throughout the demo or demo creation:
  * Gitea for the number of users selected
  * VScode for the number of users selected
  
# Application Architecture
The application deployed with this demo consists of four components:

  * Customers: The original Retail application from which the rest of microservices have been carved out. It still retains the business logic related to customer management. This legacy application runs on Tomcat and uses an Oracle database.
  * Inventory: Stores detailed information about products. Developed using Quarkus and PostgreSQL as data store. This service has been configured with the the JDK build mode for Quarkus by default.
  * Orders: Manages all order related entities. It stores only UIDs to refer to Products and Customers. Implemented with Spring Boot and using a PostgreSQL database.
  * Gateway: Access and aggregation layer for the whole application. It gets orders data and aggregates Products and Customers detailed information. Also implemented with the Spring Boot/PostgreSQL stack.
  * Frontend: A new front end layer developed with the React flavor of Patternfly, published on Nginx.


[Architecture Overview](docs/architecture.adoc)

Existing Demonstrations
- Rapid Application Deployment (docs/demo1-documentation.adoc)

