pipeline {
  agent any
  stages {
    stage('Code Checkout') {
      steps {
	    git credentialsId: '77a296bf-7451-4a38-b064-3c1d88a1b74e', url: 'https://github.com/kumar-b-baibhav/walmart-delivery-system'
      }
    }
    stage('Build') {
      steps {
            bat 'mvn clean package -DskipMunitTests'
      }
    }
    stage('Deploy') {
      steps {
            bat 'mvn deploy -DskipMunitTests -DmuleDeploy -DmuleVersion=4.4.0 -DgrantType="client_credentials" -DclientId=5fe6d27bef4b440bb7472991e4546574 -DclientSecret=ad896cb0490a4c4296D5A5426A7A49E7 -DapplicationName=walmart-delivery-sys-api -Denvironment=Sandbox -DbusinessGroup="Apisero Inc" -DworkerType=MICRO '
      }
    }
  }

}
