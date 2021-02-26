**Oppgave 1**

**A**

To run build the docker file run:

```docker build . --tag konte```

This will create a dockerimage based on the Dockerfile


**B**
To run the created image type

```docker run --name kontecontainer -p 8080:9999  konte:latest```

"-p 8080:9999" will make the application listen to port 8080 locally and forward it to the containers 9999 port.

konte:latest tells docker which docker image to run.

"--name" just names the container, insted of generating a random one

The reason I got a 404 was because it could not find the index.html file. This is because the program
relies on files that is not inside the src-folder I copy in the Dockerfile
What solved the problem was adding:
``` COPY index.html . ```
this makes docker able to access the file. Another solution would be to have the
file inside src, preferably the resources folder so we dont need to copy every file 
manually in the dockerfile.




