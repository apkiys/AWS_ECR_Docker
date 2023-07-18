# Steps to create an image and deploy to AWS ECR

01. Create new public git repository with README.md and gitignore.
02. Git clone repository into local.
03. Change path into repository locally.
04. Run "npm init".
05. Run code . to open the repository directory in VSCode.
06. Create a index.js file and input and save the relevant code.
07. Exit and go back to terminal to run "npm install express".
08. Run node index.js to test for "Running on http://0.0.0.0:8080" to make sure it works.
09. Open "localhost:8080" on local browser to make sure the page is displayed.
10. Make sure that the HOST is set to "0.0.0.0".
11. Create a file named "Dockerfile" and insert the relevant code.
12. Create a file named ".dockerignore" and insert the relevant code.
13. Login to AWS ECR with example:
    PS C:\>aws ecr get-login-password --region ap-southeast-1 | docker login --username AWS --password-stdin ************.dkr.ecr.ap-southeast-1.amazonaws.com
14. Create AWS Repository with example:
    PS C:\>aws ecr create-repository --repository-name build_repo
15. Build Docker image with example:
    PS C:\>docker build -t build_image .
16. Tag docker with example:
    PS C:\>docker tag build_image:latest ************.dkr.ecr.ap-southeast-1.amazonaws.com/build_repo:latest
    Push docker with example:
    PS C:\>docker push ************.dkr.ecr.ap-southeast-1.amazonaws.com/build_repo:latest
