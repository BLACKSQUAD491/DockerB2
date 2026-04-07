pipeline{
  agent any
  stages{
    stage('#1.Checkout'){
      steps{
        git url:'https://github.com/itsroshravi/Docker-B2',branch:'main'
      }
    }

    stage('#2. Build the Image'){
      steps{
        bat 'docker build -t mywebsite .'
      }
    }

    stage('#3. Stop all Old Containers'){
      steps{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    }

    stage('#4. Run the Image - Containerise'){
      steps{
        bat 'docker run -d -p 4000:80 --name nyconty mywebsite'
      }
    }
  }
}
