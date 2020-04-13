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
##### How to Set up Configuration Matrix

#### Run a Cron
Steps:

1. Go to organization/repository and open a Cron Job
Note: There is a "CRON" view for such kind of jobs
2. Click Build with Parameters and run Build 
3. Cron Job should trigger children jobs according to desired configuration matrix
4. When Cron Job is Completed analyze children jobs' reports/logs (Carina reports/Zafira reports/TestNG reports)

#### Schedule a Cron
#### Delete a Cron


