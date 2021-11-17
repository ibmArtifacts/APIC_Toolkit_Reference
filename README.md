# Cloud Configurations
##  1.1	Login
`apic login -s <server> --realm <admin/default-idp-1> --username <username> --password <password>`

How to get the realm: `apic identity-providers:list -s <server> --scope admin|provider`

## 1.2	Reset Password
`apic me:change-password -s server CHANGE_PASSWORD.yaml`

Content of CHANGE_PASSWORD.yaml:

current_password: OLD_PASSWORD  
password: NEW_PASSWORD  

## 1.3	Create Keystore  
`apic keystores:create -s dev2-apim.dvi1.ahfctoolkit.com -o admin keystore.json`

Content of keystore.json:  
NOTICE: the private key and public cert content must be converted properly with the \n for line breaks in actual cryptos.  
{  
	"title": "test",  
	"name": "test",  
	"summary": "",  
	"password": "password",  
	"keystore": "-----BEGIN CERTIFICATE----- \nMIIDUTCCAjmgAwIBAgIIRaMSHIh7VigwDQYJKoZIhvcNAQELBQAwIDEeMBwGA1UE\nAwwVKi5ydHAucmFsZWlnaC5pYm0uY29tMB4XDTIwMTAyODIxMDEyNVoXDTMwMTAy\nNjIxMDEyNVowIDEeMBwGA1UEAwwVKi5ydHAucmFsZWlnaC5pYm0uY29tMIIBIjAN\nBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA+sx4zopPJQWYpGljXQf3Bcr6bJI+\n4f2RjpOMSoZQiOwRSbVTpfLwH2XkK1CxCu79RBAUIQfj2upkIOEfxnWZZFnlMAHP\nhuJw7guaw4x1iA2c86FWtB9S40h1bU+CQ/J4XUkLQ0QfUbEePdlaTjUHsNeo8HwF\nK1cJcwBU3phLLLmkCaIRkMZiFe0xC0yGLAVSlC/CY6+nMX5oQfhbI8TV9hCoS6pc\nMR3XrcDB+A7K71R+1WKFRQ2MRrFymczUTF3urLds1huwx1Fnx61apwvtdOVK7u6B\nH2hufG0AyrwslbzfRjFzqvLrxoHXKp5NfSOr7GfB9Fm+MxFzEDxfoKA3IQIDAQAB\no4GOMIGLMAwGA1UdEwQFMAMBAf8wHQYDVR0OBBYEFBf7JLJxrlysUA/jVqJkQG3i\ng4dfME8GA1UdIwRIMEaAFBf7JLJxrlysUA/jVqJkQG3ig4dfoSSkIjAgMR4wHAYD\nVQQDDBUqLnJ0cC5yYWxlaWdoLmlibS5jb22CCEWjEhyIe1YoMAsGA1UdDwQEAwIC\nvDANBgkqhkiG9w0BAQsFAAOCAQEA59qfsaGIJQdukMl23HaI+QNjWqqFHoEMN1Zu\n3jP3pTEZ5cg6x7IvH2BfY6xD/ugIJwYdZ5hly22Vizkf8kzZ6jVwq0+O6eOE5jBK\nsgZIqUtlDrV1IUW5slX9YgaxKQrC3vHAzQY0TeCOjK6xxmwFWUryac9Kq8W6wYST\nYP4lRKCnGc8QiLWXC3PJnHQyltms08dY+Eut0C/fypSrJtdvp7aZ70QfyeffN6Fi\nylZ8lbrdvM6/iM0P0kdyvD794XR6YeD3sKBsZSsP5vKJrNhjkGm+s0lQunMYsWj+\nSDghPLy51d+p9e9LwrBth0FWLk1/fzajiBnC9qg4Ht4S3KT1Ng==\n-----END CERTIFICATE-----\n-----BEGIN PRIVATE KEY----- \nMIIEvAIBADANBgkqhkiG9w0BAQEFAASCBKYwggSiAgEAAoIBAQD6zHjOik8lBZik\naWNdB/cFyvpskj7h/ZGOk4xKhlCI7BFJtVOl8vAfZeQrULEK7v1EEBQhB+Pa6mQg\n4R/GdZlkWeUwAc+G4nDuC5rDjHWIDZzzoVa0H1LjSHVtT4JD8nhdSQtDRB9RsR49\n2VpONQew16jwfAUrVwlzAFTemEssuaQJohGQxmIV7TELTIYsBVKUL8Jjr6cxfmhB\n+FsjxNX2EKhLqlwxHdetwMH4DsrvVH7VYoVFDYxGsXKZzNRMXe6st2zWG7DHUWfH\nrVqnC+105Uru7oEfaG58bQDKvCyVvN9GMXOq8uvGgdcqnk19I6vsZ8H0Wb4zEXMQ\nPF+goDchAgMBAAECggEAN5WrzLLwuZbU7tOAtzS1te33tKpxD2tAoGXpOPct0Drp\n1fk/Mc93Eq5ldIgsxOyU60nY/D0gbft296aNgVG9DnWyCwLLuOxk9Q1TXrW5ss65\nk3GVotQybbc4d2Kgz2hk7t/qhB0MB/IGbtTGZADy1GnnwmzqRGHE8V0IclE0kBOg\nicv0zLKruCSub8IzdmjeiFQ+fsjSTn0KX4sCgWyQp6dHYnqk0ZayFRv2yGET22Vs\nVynHOTSGh8quwbwqkMCr6Qr/pt6lyWvs9Fm6m4J8NWalYhOEvshP468GdrNUgHZJ\nqw0w5iv6CK0MvnpIkdrpPDtbRSfur9BoykTeVCNTwQKBgQD/6ax6v/TcTfc42pYN\nNHM1rgSAorxBCKXBByi/Lnc5fH10guj4heeuqCjPXOI9nPc+fmCwqdBdZnDdvS9T\nlwWgx8jIu0OV8/K7QsguIPqpPAbMsGpdkm0cnp2bNP5RXA2bAPB1wzMO4nDMkGNo\nMa7RdoUIpCR37Rl1SuLPPaERyQKBgQD64locQlBTV50GTMui0K9D6rhYqlmoDZwh\n1cdpr0dV3bziXKmAo8zSnGhzZutEAww8HgGqQRw6u1wejo5yJtgpEEFpk0Tflmkn\nbfQMy31mRnXbzSxDzHuZSDrnyLdU5JQIul+ATf43OVn3Iqm8s9Jr99ulwiYVr640\nCxRby1LmmQKBgAobFDCUu/qnKYgZOauz0ojgIlViF8UJrmH9AmLqVtLyU5HySXjm\n8Ms44MOvi0+bjzfsjazsR8oobXSUL/ZBFHvQ5+DlZDnbtE4oyPbpXnyoXixfGxQu\n4BgtO1QRt6lG1VK1qsk7uBxyXLn3SbWnoJus7nv032vM9SBooKRGbsHhAoGAaMWo\njg6fjv6Sw/PEQv1VhE58qAKUKJtuba7idV9OsixE2l+KJf/B5N6OvErpy2Bedqit\nV1WTnW9rPBOap09TjGqOdrGa3Kjqxx2jAsjkWJbqV12qs7GsmEnS18M51MkUjUSP\n53wqwxM/X/bo3bZXFOHQp7uZvgq8/Fz4JpGV0FkCgYBmeemQfVuzzTOUkA3aWj6R\nQn+hHmJVM6z1zkytMsN0+2tp5kHP/95+C4TXWq6si+sUcSLMoM/mlb8Wjnb2H9xY\nnjc/bZqTrzn6EU4ehAz1CqnMrFRoNk4B56yCd1c8+EjziIPbdrOTQQMOEZi8GSW+\nx4ua6l4RaSXIXRTusQjtwA==\n-----END PRIVATE KEY-----\n"  
}  

## 1.4	Create TLS Profile  
`apic tls-server-profiles:create -s <server> -o admin new-server-profile.yaml`

new-server-profile.yaml:  
    
type: tls_server_profile  
api_version: 2.0.0  
name: new-client-profile  
version: 1.0.0  
title: New TLS client profile  
summary: New TLS client profile  
protocols:  
&nbsp;  \- tls_v1.2  
ciphers:  
&nbsp;  \- ECDHE_ECDSA_WITH_AES_256_GCM_SHA384  
&nbsp;  \- ECDHE_RSA_WITH_AES_256_GCM_SHA384  
&nbsp;  \- ECDHE_ECDSA_WITH_AES_256_CBC_SHA384  
&nbsp;  \- ECDHE_RSA_WITH_AES_256_CBC_SHA384  
&nbsp;  \- ECDHE_ECDSA_WITH_AES_256_CBC_SHA  
&nbsp;  \- ECDHE_RSA_WITH_AES_256_CBC_SHA  
&nbsp;  \- DHE_DSS_WITH_AES_256_GCM_SHA384  
&nbsp;  \- DHE_RSA_WITH_AES_256_GCM_SHA384  
&nbsp;  \- DHE_RSA_WITH_AES_256_CBC_SHA256  
&nbsp;  \- DHE_DSS_WITH_AES_256_CBC_SHA256  
&nbsp;  \- DHE_RSA_WITH_AES_256_CBC_SHA  
&nbsp;  \- DHE_DSS_WITH_AES_256_CBC_SHA  
&nbsp;  \- RSA_WITH_AES_256_GCM_SHA384  
&nbsp;  \- RSA_WITH_AES_256_CBC_SHA256  
&nbsp;  \- RSA_WITH_AES_256_CBC_SHA  
&nbsp;  \- ECDHE_ECDSA_WITH_AES_128_GCM_SHA256  
&nbsp;  \- ECDHE_RSA_WITH_AES_128_GCM_SHA256  
&nbsp;  \- ECDHE_ECDSA_WITH_AES_128_CBC_SHA256  
&nbsp;  \- ECDHE_RSA_WITH_AES_128_CBC_SHA256  
&nbsp;  \- ECDHE_ECDSA_WITH_AES_128_CBC_SHA  
&nbsp;  \- ECDHE_RSA_WITH_AES_128_CBC_SHA  
&nbsp;  \- DHE_DSS_WITH_AES_128_GCM_SHA256  
&nbsp;  \- DHE_RSA_WITH_AES_128_GCM_SHA256  
&nbsp;  \- DHE_RSA_WITH_AES_128_CBC_SHA256  
&nbsp;  \- DHE_DSS_WITH_AES_128_CBC_SHA256  
&nbsp;  \- DHE_RSA_WITH_AES_128_CBC_SHA  
&nbsp;  \- DHE_DSS_WITH_AES_128_CBC_SHA  
&nbsp;  \- RSA_WITH_AES_128_GCM_SHA256  
&nbsp;  \- RSA_WITH_AES_128_CBC_SHA256  
&nbsp;  \- RSA_WITH_AES_128_CBC_SHA  
server_name_indication: true  
keystore_url: >-  
&nbsp;  https://cloud.192.168.1.21.nip.io/api/orgs/6ec7d8cc-29f9-4c90-beb1-6f07871f67c8/keystores/9e237907-16b2-4190-8e56-59dc8d3a7129  
truststore_url: >-  
&nbsp;  https://cloud.192.168.1.21.nip.io/api/orgs/6ec7d8cc-29f9-4c90-beb1-6f07871f67c8/truststores/b4695ff9-a4dc-419d-93c9-3b98167c6ed1  
visibility:  
&nbsp;  type: private  
  
Dependent calls:  
keystore_url: `apic keystores:list -s <server> -o admin`  
truststore_url: `apic truststores:list -s <server> -o admin`  

  

# APIM Configurations
