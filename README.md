# one-way-ssl-mule-project

Step 1: Generate server side keystore

keytool -genkey -alias mulesoft-server -keysize 2048 -keyalg RSA -keystore server-keystore.jks

In this command:
- alias : We can give any name
- keysize : 2048(default)
- key algorithm : RSA
- keystore server-keystore.jks

Example: 

D:\keys>keytool -genkey -alias mulesoft-server -keysize 2048 -keyalg RSA -keystore server-keystore.jks ----> press enter

Enter keystore password:
What is your first and last name? ----> press enter
  [Unknown]:
  
What is the name of your organizational unit? ----> press enter
  [Unknown]:
  
What is the name of your organization? ----> press enter
  [Unknown]:
  
What is the name of your City or Locality? ----> press enter
  [Unknown]:
  
What is the name of your State or Province? ----> press enter
  [Unknown]:
  
What is the two-letter country code for this unit? ----> press enter
  [Unknown]:
  
Is CN=Unknown, OU=Unknown, O=Unknown, L=Unknown, ST=Unknown, C=Unknown correct?
  [no]:  yes ----> Type enter "Yes" and then enter

Step 2:

To Export the public certificate from server keystore.

keytool -export -alias mule -keystore server-keystore.jks -file server-trust.crt

Step 3: 

Import server public certificate into client Truststore

keytool -import -alias mulesoft-server -keystore client-truststore.jks -file server-trust.crt

  
