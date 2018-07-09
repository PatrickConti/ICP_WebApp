# ICP_WebApp

The Dockerfile provided is multiarchitecture and includes all dependencies for this simple webapp.
The WebApp connects to a MongoDB Container exposed from the IBM Cloud Private Platform through a service.
NN will refer to the Linux guest you will be using in the lab.

After pulling, you will need to "build" the image using Docker build -t "container name"
I called mine vmongo, which you see below in the Docker Run command.

DOCKER RUN Command to run "vmongo" and pass in database address
docker run -e "MONGO_URL=mongodb://192.168.176.4:31439/nodetest2" -p 87NN:8768 vmongo 

This passes the address of the mongoDB in the cloud as an environment variable, with an exposed service at port 31439.
This means that incoming API calls will work with port 31439 to manipulate the MongoDB address.
-P indicates what port the webapp will run at

For this particular setup, you have to be VPNed into the "namespace" where 31088 was exposed. 
Please contact me and I can provide details on how to VPN into the proper subnet and access this namespace.
Once SSHed in, the url used to access the webapp is: http://192.168.176.NN:87NN/
