# flask-app


To document the CI/CD pipeline steps and the reasons behind the
 tools chosen, you can update your README file with the 
 
 following information:

**CI/CD Pipeline Steps**

Trigger: The pipeline is triggered on pushes to the main branch.

Checkout: The pipeline checks out the code from the repository
 using the actions/checkout action.

Set up Python: The pipeline sets up the Python environment with
 version 3.x using the actions/setup-python action.

Install dependencies: The pipeline upgrades pip and installs 
dependencies from requirements.txt using the pip install 
command.

Run tests: The pipeline runs tests using the python test_app.py 
command.

Deploy to AWS Elastic Beanstalk (EB):
Condition: Deployment is triggered if all previous steps are 
successful.

Tools: AWS Elastic Beanstalk is used for deployment.
Reason: Elastic Beanstalk is a Platform as a Service (PaaS) 
offering from AWS that makes it easy to deploy and manage 
applications. It automatically handles the deployment, from 
capacity provisioning, load balancing, and auto-scaling to application health monitoring.

Steps:
Initialize Elastic Beanstalk application: eb init -p python-3.7 
$EB_APP_NAME --region $AWS_REGION

Create an environment in Elastic Beanstalk: eb create 
$EB_ENV_NAME

Deploy the application to the environment: eb deploy


**Reasons Behind Tool Choices**

GitHub Actions: Chosen for its seamless integration with GitHub 
repositories, allowing us to define CI/CD workflows using YAML 
files directly in the repository.

Python: Used as the programming language for the application, 
and for running the tests and the deployment scripts.

Elastic Beanstalk: Chosen for its ease of use and scalability. 

Elastic Beanstalk abstracts away the complexities of 
infrastructure management, allowing us to focus on deploying 
and managing our application.

