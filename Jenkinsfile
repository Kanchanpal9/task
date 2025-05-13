node {
    stage('Checkout') {
        git 'https://github.com/Kanchanpal9/task.git'
    }

    stage('Build') {
        sh 'docker build -t myapp .'
    }

    stage('Run') {
        sh 'docker run -d -p 3000:3000 myapp'
    }
}
