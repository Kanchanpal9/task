✅ Objective: Set up a basic Jenkins pipeline to automate the process of building and deploying an
application.

✅ Tools Used: Docker, Jenkins, Github, Sample Application(Node.js)

✅ Deliverable
Jenkinsfile – a declarative pipeline to:

Build the app

Run basic tests

Deploy the Docker container

Step 1: Launch an EC2 Instance

Step 2: Install Jenkins
![Screenshot 2025-05-13 122352](https://github.com/user-attachments/assets/987586d8-bef9-4919-a7fd-27d8c16185fe)

Step 3: Install Plugin In Jenkins
 Docker
 Git(By Default)
 
Step 4: Create Jenkins file in Github
node {
    stage('Checkout') {
        git branch: 'main', url:'https://github.com/Kanchanpal9/task.git'
    }

    stage('Build') {
        sh 'docker build -t myapp .'
    }

    stage('Run') {
        sh 'docker run -d -p 3000:3000 myapp'
    }

  Step 4: Configure Jenkins Job
Open Jenkins UI → New Item → Choose Pipeline

![Screenshot 2025-05-13 123712](https://github.com/user-attachments/assets/6140212c-1a87-49b7-a293-a2d1fce7988c)


Under Pipeline > Definition, choose Pipeline script from SCM

Set the Git repo URL and specify the Jenkinsfile path (default: Jenkinsfile)

Save and run.

![Screenshot 2025-05-13 130934](https://github.com/user-attachments/assets/17e9bf3d-7c8e-45c7-82a8-a6769f9bf62e)
