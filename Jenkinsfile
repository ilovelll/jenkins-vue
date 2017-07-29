node {


  nodejs(nodeJSInstallationName: 'node8') {
      // some block

      try {

        //  stage('Checkout'){

        //     checkout scm
        //  }

        stage('Test'){

          env.NODE_ENV = "test"

          print "Environment will be : ${env.NODE_ENV}"

          bat 'node -v'
          bat 'npm prune'
          bat 'npm install'
          bat 'npm test'

        }
        stage('Build'){
          bat 'npm run build'
        }

        stage('Deploy'){

          echo 'Push to Repo'
          //  sh './dockerPushToRepo.sh'

          //  echo 'ssh to web server and tell it to pull new image'
          //  sh 'ssh deploy@xxxxx.xxxxx.com running/xxxxxxx/dockerRun.sh'

        }

        stage('Cleanup'){

          echo 'prune and cleanup'
          //  sh 'npm prune'
          //  sh 'rm node_modules -rf'

          //  mail body: 'project build successful',
          //              from: 'xxxx@yyyyy.com',
          //              replyTo: 'xxxx@yyyy.com',
          //              subject: 'project build successful',
          //              to: 'yyyyy@yyyy.com'
        }



      }
      catch (err) {

          // currentBuild.result = "FAILURE"

          //     mail body: "project build error is here: ${env.BUILD_URL}" ,
          //     from: 'xxxx@yyyy.com',
          //     replyTo: 'yyyy@yyyy.com',
          //     subject: 'project build failed',
          //     to: 'zzzz@yyyyy.com'

          // throw err
      }
  }

}