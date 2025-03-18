keytool -genkey -keyalg RSA -alias *.dev-appcentre.faysalbank.com -keystore jenkins.keystore -storepass fbl2021 -validity 365 -keysize 2048

docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword

b59a4ef2819f44199fa7631da4b783f4
