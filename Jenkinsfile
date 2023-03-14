node('MAVEN_JD8'){
    stage('version control'){
        git url :'https://github.com/dkrishnakanthgoud/game-of-life.git',
          branch :'scripted'
    }
      stage('build'){
        sh 'export PATH="/usr/lib/jvm/java-1.8.0-openjdk-amd64/bin:$PATH" && mvn package'

      }
       stage('postbuild'){
         archiveArtifacts  onlyIfSuccessful: true,
            artifacts:'**/Target/gameoflife.war',
            allowEmptyArchive: true,
       } 
        stage('test results'){
          junit testResults :'**/superfire-reports/TEST-*.xml',
            allowEmptyResults :true
        }
       
        
}      