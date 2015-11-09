# jenkins_ubuntu15_lib32
This is a docker automated build project. The image contains jenkins and the lib pkg i386 for android sdk


# Usage

```
docker run -d --dns 8.8.8.8 -p 8080:8080 -p 50000:50000 -v /home/local/android-sdk-linux:/android-sdk-linux -v /your/home:/var/jenkins_home jenkins_ubuntu15_lib32
```
In above command: 
"-d" :background exec jenkins.
"--dns 8.8.8.8" :specify the default outer DNS server.
"-p 8080:8080" : configure the 8080 port for jenkins web server.



```
docker run -d --dns 8.8.8.8 -p 8080:8080 -p 50000:50000 -v /home/local/android-sdk-linux:/android-sdk-linux jenkins_ubuntu15_lib32
```
"-v /home/local/android-sdk-linux:/android-sdk-linux"  : This image will not install android-sdk, hence you may want to make that a persisten volume to mock a android sdk from local disk. 



```
docker run -d --dns 8.8.8.8 -p 8080:8080 -p 50000:50000  -v /your/home:/var/jenkins_home jenkins_ubuntu15_lib32
```
This will store the workspace in /var/jenkins_home. All Jenkins data lives in there - including plugins and configuration.
You will probably want to make that a persistent volume (-v /your/home:/var/jenkins_home):