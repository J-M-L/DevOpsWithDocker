#3.7 B

Docker can be used to reduce trouble of setting up/maintaining programs. With container you need to write Dockerfile that is recipe for your container. It contains information of what OS container is using, commands that needs to be run on OS, and other commands. After writing Dockerfile once, you can build an image from it, that image can be used on Mac, PC, Linux to create container that contains your app. This enables you to run your application on many platforms with one simple command “Docker run ……”. Docker containers doesn’t need to be user friendly from within, since required item can be bind outside, that enables that all unnecessary programs can be uninstalled and this makes images smaller than without Docker is hard to achieve. 


Without Docker you need to transfer your program on every machine separately, also you need to install OS, other required application, config environment variables, etc… This also creates problems with previous versions of programs i.e. if you are using older version of some program and need newer one now, without Docker you need to clear all unnecessary programs from platform, while in docker you basically can start from fresh install easily and fast. 


Docker also adds some security by not allowing access from container to outside network or volumes without user first accepting it. 
