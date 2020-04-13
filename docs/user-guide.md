## User Guide
### Test Jobs(API/Web/Mobile)
Jenkins Pipeline Job - this is a job that can be created for each suite and can be executed on demand or by schedule. 

#### Create a Job
#### Run a Job
Steps:

1. Go to organization/repository and open a Job

2. Click Build with Parameters and run Build 

3. When Job is Completed analyze published reports/logs (Carina reports/Zafira reports/TestNG reports)

#### Schedule a Job
#### Delete a Job

### Cron Jobs(Layer of testing)
Jenkins Pipeline Cron - this is a job that can include different suites/jobs and can be executed on demand or by schedule.

#### Create a Cron
#### Run a Cron
#### Schedule a Cron
#### Delete a Cron

### How to Run Web-Demo-Test job
 
 

### How to Run API-Demo-Test job(should be passed)
 Preconditions:

Jenkins is started
Organization is created
Repo is registered

 Steps:

1. Go to qaprosoft/carina-demo and start API-Demo-Test job ->

<b> Pipeline API-Demo-Test job is opened </b> 

2. Click Build with Parameters and run Build ->

<b> Pipeline API-Demo-Test job is started </b> 

3. Open Jenkins and verify that web tests are running in web node

4. Open Build History in API-Demo-Test and select Zafira Report

5. Click "Logs" and verify that the report looks correctly

### How to Run nightly_regression job
 Preconditions:

Jenkins is started
Organization is created
Repo is registered

 Steps:

1. Go to qaprosoft/carina-demo and start nightly_regression job ->

<b> Nightly_regression job is opened </b> 

2. Click Build with Parameters and run Build ->

<b> Pipeline Nightly_regression is started </b> 

3. Open Jenkins and verify that web tests are running in web node

4. Go to "qaprosoft/carina-demo" and verify that API-Demo-Test, API-DataProvider, SOAP-Demo,Tags-Demo-Test,API-CustomParams, Web-Demo-Single-Driver are completed and Passed.
Web-Demo-Test is completed and failed.

### How to Run full_regression job
 Preconditions:

Jenkins is started
Organization is created
Repo is registered

 Steps:

1. Go to qaprosoft/carina-demo and start full_regression job

 <b> Full_regression job is opened</b> 

2. Click Build with Parameters and run Build

 <b> Pipeline full_regression job is started</b> 

3. Open Jenkins and verify that web tests are running in web node

4. Go to qaprosoft/carina-demo and verify that API-Demo-Test, API-DataProvider-Classes, SOAP-Demo, Tags-Demo-Test, API-CustomParams, Web-Demo-Single-Driver-Test, Mobile-Android-Demo-Test, Mobile-iOS-Demo-Test are completed and Passed.
Web-Demo-Test, API-DataProvider-Classes are completed and failed.


