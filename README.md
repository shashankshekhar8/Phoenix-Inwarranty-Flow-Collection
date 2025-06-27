# Postman API Automation Integration with Github Actions #

This repository is a demonstration for POC for integrating postman tests with Github Actions. The tests are written in postman and they are executed on the VM with the help of newman and newman-reporter-htmlextra.
Github Actions will trigger the project execution on every push to the main branch. You can also execute the project manually using workflow_dispatch. The project runs on a scheduled time with the help of cron job.

The HTML report is archived and kept in the artifact section for the team to download it. Along with that they can view the report directly from github page : https://shashankshekhar8.github.io/Phoenix-Inwarranty-Flow-Collection/ .
The latest report is mailed to the team memebers using GMAIL SMTP.

## Testing Coverage ##
1. Happy Flow Testing
2. Negative and Edge Case Testing
3. Token Testing
4. Data Driven Testing with CSV
5. Schema Validation
6. Secrets Management with Github Secrets

## Tech Stack ##
1. Postman
2. NodeJs 22v
3. Newman
4. Newman-Reporter-Htmlextra
5. Github Actions
6. Gmail SMTP
7. Github Pages
8. CSV for Data Driven Testing
9. AWS-EC2 instance for Self hosted github runner

## Github Pages ##
You can directly view the latest report of the Postman tests at the Github Pages link : https://shashankshekhar8.github.io/Phoenix-Inwarranty-Flow-Collection/

## HTML Report ##
The report will be created in the newman folder in root directory of your project
![Postman Report](https://github.com/shashankshekhar8/Phoenix-Inwarranty-Flow-Collection/blob/static-content/Newman-Report.PNG)

## Project Structure ##
```
Phoenix Inwarranty Flow Collection
├─ Inwarranty-flow Collection.postman_collection.json  # Collection File
├─ QA.postman_environment.json  # Environment File
└─ testData.csv  # TestData File

```

## How to run the Project? ##
You can run the project on your local system for that:
1. Clone the project on Local System: https://github.com/shashankshekhar8/Phoenix-Inwarranty-Flow-Collection.git
2. Install Nodejs and NPM from https://nodejs.org/en/download
3. Install Newman using ```npm install -g newman```
4. InstallNewman-Reporter-HtmlExtra using ```npm install -g newman-reporter-html```
5. Run the newman command

               newman run 'Inwarranty-flow Collection.postman_collection.json' \
              -e QA.postman_environment.json \
              -d testData.csv \
              -r cli,htmlextra \
              --reporter-htmlextra-export ./newman/index.html





