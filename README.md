# ICP_WebApp

The Dockerfile provided is multiarchitecture and includes all dependencies for this simple webapp.
The WebApp connects to a MongoDB Container exposed from the IBM Cloud Private Platform through a service.
NN will refer to the Linux guest you will be using in the lab, and the corresponding ICP namespace.

After cloning to your local machine, you will need to "build" the image using Docker build -t teamNN-webapp .
I called mine team63-webapp, which you see below in the Docker Run command. You will use your teamNN name.

DOCKER RUN Command to run "teamNN-webapp" and pass in database address
docker run -e "MONGO_URL=mongodb://192.168.176.4:30883/nodetest2" -p 87NN:8768 teamNN-webapp 

This passes the address of the mongoDB in the cloud as an environment variable, with an exposed service at port 30883.
This means that incoming API calls will work with port 30883 to manipulate the MongoDB address.
-P indicates what port the webapp will run on.

For this particular setup, you have to be VPNed into the ICP environment where 30883 was exposed. 
Please contact me and I can provide details on how to VPN into the proper subnet.
Once SSHed in, the url used to access the webapp is: http://192.168.176.NN:87NN/
