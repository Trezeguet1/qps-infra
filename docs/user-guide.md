### Easy to Use Jenkins
### Update Jenkins credentials (Described in Config guide)
 Preconditions:

  Jenkins is installed and started
 
<b> Steps:</b>

1.Open Jenkins
2.Click on Credentials in the left menu
3.Select "ghprbhook-token" and click on the link
4.Click on Update in the left menu
5.Enter Username e.g."username"
6.Near Password click Change password
7.Enter value of "Git token access" that was generated before for this user
8.Save changes


### How to RegisterOrganization
 Preconditions:

1.Jenkins is started          
2.Open Jenkins in Browser 
3.Open jenkins/configure and change value of branch QPS_PIPELINE_GIT_BRANCH to “master”
4.Open Management_Jobs folder 

 Steps:                                                       

1.Tap on Register Organization ->
<b> Pipeline RegisterOrganization is opened </b>

2. Tap Build with Parameters in right top menu
3. Enter folder name - select your name e.g. "organization"
4. Tap Build  ->
 <b>Pipeline RegisterOrganization is done </b> 

### How to RegisterRepository
 Preconditions:

Open my organization that was created e.g. jenkins/okamara

 Steps:  

1. Tap RegisterRepository

 <b> Pipeline RegisterRepository page is opened </b> 

2. Verify that the following values are preset up in the fields:
scmHost - github.com,
scmOrg is entered e.g. okamara,
branch - master,
pipelineLibrary - QPS-Pipeline,
runnerClass - com.qaprosoft.jenkins.pipeline.runner.maven.QARunner

<b> The following values are preset up in the fields: scmHost - github.com, scmOrg is entered e.g. okamara , branch - master, pipelineLibrary - QPS-Pipeline, runnerClass - com.qaprosoft.jenkins.pipeline.runner.maven.QARunner </b> 

3. Enter scmuser - e.g. okamara,
scmTocken - enter your token (should be generated on 
gihub for your user),
repo - e.g. ”carina-demo”

4. Tap Build ->

<b> Build is successful</b> 

5. Verify that carina-demo contains jobs: onPullRequest-carina-demo-trigger and 
onPullRequest-carina-demo ->

<b> carina-demo contains jobs: onPullRequest-carina-demo-trigger and 
onPullRequest-carina-demo</b> 


#### How to Create fork via Github (Described in Config guide)
#### How to Configure Webhook via GitHub (Described in Config guide)
#### How to Send Pull request via github (Described in Config guide)
#### How to Close/Restart Pull request via github (Described in Config guide)

### How to Run Web-Demo-Test job
 Preconditions:

Jenkins is started
Organization is created
Repo is registered

 Steps:

1. Go to qaprosoft/carina-demo and start Web-Demo-Test ->

<b> Pipeline Web-Demo-Test is opened </b>

2. Click Build with Parameters and run Build ->

 <b> Pipeline Web-Demo-Test is started </b> 

3. Open Jenkins and verify that web tests are running in web node

4. Open Build History in Web-Demo-Test and select Zafira Report ->

<b> Zafira report Web-demo-test in opened </b> 

5. Verify that Web-Demo-Test should be failed

6. Click "Logs" and verify that the report had status "failed"

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


