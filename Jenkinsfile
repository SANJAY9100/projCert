pipeline{
agent any
stages{
stage('clone repository')
{
steps{
git 'https://github.com/SANJAY9100/projCert.git'
}
}
  stage('Build Image')
  {
    steps
    {
      sh 'sudo docker build website/. -t pipe:$BUILD_NUMBER'
    }
  }
  stage('Deploy Image')
  {
    steps
    {
      sh 'sudo docker rm -f qw'
      sh 'sudo docker run -itd --name qw -p 8009:80 pipe:$BUILD_NUMBER'
    }
  }
  
}
}
