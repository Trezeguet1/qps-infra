# QPS-Infra - Configuration Guide


### Easy to Use Jenkins
 Preconditions:

 Jenkins is installed and started
<b> Generate "Git personal access token" </b>
1. Sign in to github
2. In Left menu select "Settings" from the list
3. Select "Developer settings"
4. Select "Personal access token"
5. Click "Generate token"
6. Remember it or save

### 1:Update Jenkins credentials
 
Steps:
1.Open Jenkins
2.Click on Credentials in the left menu
3.Select "ghprbhook-token" and click on the link
4.Click on Update in the left menu
5.Enter Username e.g."username"
6.Near Password click Change password
7.Enter value of "Git Personal access token" that was generated before for this user
8.Save changes
9.Open Jenkins/Manage Jenkins/Configure System
10.Scroll till "GitHub Pull Request Builder" -> Credentials are populated here


### 2:RegisterOrganization (described in User Guide)


## 3:RegisterRepository (described in User Guide)


### 4:Create fork via Github
 Preconditions:
Github account is created for you

 Steps:  

1. Sign in to Github with your user account https://github.com/
2. Open My profile
3. Go to qaprosoft/carina-demo
4. Tap Fork
5. Verify that organization/carina-demo repository is created -> 

 <b> organization/carina-demo repository is created </b> 

## 5:Configure Webhook via GitHub
Preconditions:

Open https://github.com

Steps:  

1. Sign in with your user account
2. Open created before your repository e.g. organization/carina-demo 
3. Open Settings
4. Open Webhooks in menu
5. Tap Add Webhook
6. Enter Payload URL e.g. .../jenkins/ghprbhook/
7. Select application/x-www-form-urlencoded in "Content Type" field
8. Select "Let me select individual events" with "Issue comments" and "Pull requests enabled" option
9. Click "Add webhook" button -> 
<b> Webhook is created </b>
  
### 6:Send Pull request via github 
 Preconditions:
Fork Repository if need it via Github
Update ghprbhook Credentials in Jenkins
Open jenkins/configure

Steps:

1. In GitHub select "Your repository"/"project"/"Pull requests"
2. Create a new Pull request
3. Enter Comment to post e.g. “Comment”
4. Tap “Comment to Issue”
5. Verify that comment is set via Pull request ->
<b> Pull Request is created </b>

TBD:
In Jenkins
6. Verify that onPullRequest jobs are started 
7. Verify that onPullRequest jobs are completed ->

 <b> The following jobs onPullRequest-carina-demo-trigger and 
onPullRequest-carina-demo are run with Success </b> 

### 7:Close/Restart Pull request via github
 Preconditions:
 Sign in to Github
Open the pull request in GitHub for your repository/project

 Steps:

1. Tap “Close pull request”
2. Tap “Reopen pull request”
3. Verify that onPullRequest jobs are started 
4. Verify that onPullRequest jobs are completed ->

 <b> The following jobs onPullRequest-carina-demo-trigger and 
onPullRequest-carina-demo are run with Success </b> 

###  Workaround to run jobs without errors(.m2 folder)
 Preconditions:

If onPullRequest-carina-demo and onPullRequest-carina-demo-trigger job run with errors like e.g.
[ERROR] Could not create local repository at /var/jenkins_home/.m2/repository -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]

 Steps:

1. Run the following commands via terminal:
sudo chown -R ubuntu:ubuntu ~/.m2
sudo chmod -R a+rws ~/.m2
./stop.sh
docker-compose rm -fv
./start.sh

2. Stop/Resend pull request via github and verify that jobs onPullRequest-carina-demo and onPullRequest-carina-demo-trigger run without errors
 
### Workaround for "Error grabbing Grapes"(.m2) during create organization or start jobs
 Preconditions:

If onPullRequest-carina-demo and onPullRequest-carina-demo-trigger job run with errors like e.g.
[ERROR] General error during conversion: Error grabbing Grapes -- [download failed: org.beanshell#bsh;2.0b4!bsh.jar]

 Steps:

1. remove completely $HOME/.m2/repository and QPS_HONE/jenkins/.groovy/grapes content to allow jenkins to redownload everything from scratch

Run the following commands via terminal:
./stop.sh
sudo rm -rf ~/.m2/repository
cd ~/tools/qps-infra
rm -rf ./jenkins/.groovy/grapes
./start.sh

### 8:Run Web-Demo-Test job(described in User Guide)
### 9:Run API-Demo-Test job(described in User Guide)
### 10:Run nightly_regression job(described in User Guide)
### 11: Run full_regression job(described in User Guide)
 


