# frontendSample for a weeklyPlanner

## Technologies used

- Angular
- Ajax
- HTML5
- CSS3 and SASS

## Project Structure

- FrontendSample // This repository
- BackendSample // https://github.com/apokochito/backendSample
- SecuritySample // https://github.com/apokochito/securitySample
- ValidationJobSample // https://github.com/apokochito/validationJobSample

### Jenkins integration (only for development references)

Installation steps (by windows option)

- Download Jenkins from https://www.jenkins.io/download/#downloading-jenkins
- Run service as LocalSystem (not recommended)
- Configure port Number 9040 and open chrome using http://localhost:9040
- Set local system password
- Plugins nstallation process...
- Create admin user
- Instance configuration with (http://localhost:9040)

Note: Make sure that you have all necessary plugins, Maven, Git, and Java tools already configured in Jenkins.

Create pipeline

- From home page, select "New Item" and name it as Frontend
- Select "Freestyle Project"
- Go to Settings and add the GitHub url for that project
- Configure GitHub and Heroku repositories/credentials as following...

	Github

	- Add repository URL
	- Add your account credentials
	- Add a brief description of those credentials
	- Leave ID field empty

	Heroku
	
	- Add git repository URL of your app from heroku portal
	- Add your account credentials (email), and run this following commands to get your respective password (use your git CLI)
	1. $heroku login
	2. $heroku auth:token

- Add a Build (Maven) as "package"
- Add another build to publish to Heroku "git push heroku master" (consider that if your build fails is going to be deployed no matter what)
- Run your build
