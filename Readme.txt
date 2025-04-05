keytool -genkey -keyalg RSA -alias *.dev-jenkinstest.com -keystore jenkins.keystore -storepass jenkins123 -validity 365 -keysize 2048

docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword

b59a4ef2819f44199fa7631da4b783f4
