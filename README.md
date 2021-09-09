Build the docker using following command

<docker buildx build -t backend:first> . # where first represents the image tag
  
Then run the container based upon the image created in first step  
 <docker run -it --name backend -p 8080:8080 backend:first>

Run the jenkins pipeline for both front end and backend
