#Solution to Containize
The app server.py is containerized in python 3.6.7 the  docker container, containerize_app_1 with Flask 1.1.1 and Gunicorn 19.9.0 install.
The application is located in the /home/app/server directory.  I installed vim as my text editor.

The nginx container uses a docker volume, ssl_certifcates, to store the ssl certificates.  All https requests are redirected to https and strict-transport security is enforced.   Only TLS v.1.2 and TLS v.1.3 are supported.   Please note that proxy pass was changedfrom http://127.0.0.1:8000 was changed to my VM IP address 10.0.0.250:8000 since the nginx and app containers would not connect.

The following is outputed on curl -k https://localhost/ 

demo@ubuntu:~/containerize/nginx$  curl -k https://localhost/
It's easier to ask forgiveness than it is to get permission.
X-Forwarded-For: 172.27.0.1
X-Real-IP: 172.27.0.1
  
Please note that validate.sh didn't need see the above, but I can see the output in command line and my browwser of curl -k https://localhost/ 
