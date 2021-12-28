pipeline {
  agent any
  stages {
    stage('Code Checkout') {
      steps {
	    git credentialsId: '4b22c39f-9efb-4a4f-9662-d23339dc978a', url: 'https://github.com/kumar-b-baibhav/book-my-holiday-flights-sys'
      }
    }
    stage('Build') {
      steps {
            bat 'mvn clean package'
      }
    }
    stage('Deploy') {
      steps {
            bat 'mvn deploy -DskipMunitTests -DmuleDeploy -DmuleVersion=4.4.0 -DgrantType="client_credentials" -DclientId=5fe6d27bef4b440bb7472991e4546574 -DclientSecret=ad896cb0490a4c4296D5A5426A7A49E7 -DapplicationName=walmart-delivery-sys-api -Denvironment=Sandbox -DbusinessGroup="Apisero Inc" -DworkerType=MICRO '
      }
    }
  }

}
