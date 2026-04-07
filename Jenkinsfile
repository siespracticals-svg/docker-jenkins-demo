pipeline{
  agent any
  stages{
    stage('#1. Checkout'){
    steps{
      git url:"https://github.com/siespracticals-svg/docker-jenkins-demo",branch:"main"
    }
  }
    stage('#2. Build the Image'){
      steps{
        bat 'docker build -t mywebsite .'
      }
    }

    stage('#3. Stop all old containers'){
      steps{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    }
    
    stage('#4. Run the image - Conainerise'){
      steps{
        bat 'docker run -d -p 4005:80 --name mycont mywebsite'
      }
    }
}
}
