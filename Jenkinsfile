pipeline {
  agent any
  stages{
    stage("updating demployment file"){
      steps{
      echo "updating deployment.yaml file"
       withCredentials([usernamePassword(credentialsId: 'github', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
                        //def encodedPassword = URLEncoder.encode("$GIT_PASSWORD",'UTF-8')
                        sh "git config user.email gamertech996@gmail.com"
                        sh "git config user.name gamertech1"
                        //sh "git switch master"
                        sh "cat deployment.yaml"
                        sh "sed -i 's+gamertech1/django-app.*+gamertech1/django-app:${BUILD_NUMBER}+g' deployment.yaml"
                        sh "cat deployment.yaml"
                        sh "git add ."
                        sh "git commit -m 'Done by Jenkins Job changemanifest: ${BUILD_NUMBER}'"
                        sh "git push https://${GIT_USERNAME}:${GIT_PASSWORD}@github.com/${GIT_USERNAME}/sample-project-gradle.git HEAD:master"

          
       }}
    }
  }
}
