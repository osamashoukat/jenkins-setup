keytool -genkey -keyalg RSA -alias *.dev-jenkinstest.com -keystore jenkins.keystore -storepass jenkins123 -validity 365 -keysize 2048

docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword

3608cab73db24c0199ef559e2f9fb558

jenkins.admin
Jenkins User ID: jenkinsadmin123
Password: jenkins@1234
