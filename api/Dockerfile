#THIS SPECIFY RUN TIME ENVIRONMENT FOR OUR APPLICATION..IT RUNS ON NODE AND A SMALL LINUX DISTRIBUTION CALLED ALPINE
FROM node:16-alpine 

RUN npm install -g nodemon

#THIS IS OUR WORKING ROOT DIRECTORY FOR OUR IMAGE THATS GONNA BE BUILT ON DOCKER RUN THIS FILE
WORKDIR /app

COPY package.json .

RUN npm install

# HERE WE ARE COPYING OUR FILES like app.js and package and all others from root specified with first dot and the second dot is basically a folder within docker work directory
# which is /app that we created above and we copying our file from our pc root folder to the docker root 
COPY . .

# Once we are done CREATING our RUN-TIME ENVIRONMENT[NODE] and INSTALLING SMALL LINUX DISTRO[ALPINE]
# we are then running this command to INSTALL DEPENDENCIES our APPLICATION NEEDS from PACKAGE.JSON within the DOCKER WORKDIR[/app]

# We here are exposing the PORT within the PROCESS of the ISOLATED DOCKER INSTANCE
EXPOSE 4000


# This here is basically COMPUTER ON and got TERMINAL OPENED and then RUNNING our COMMAND NODE APP.JS
CMD ["npm","run","dev"]

#  IMPORTANT make sure YOU CREATED .dockerignore FILE to ignore any file or folder you dont want docker to copy it into its isolated process[CONTAINER]
#  for example node_modules a big one

# and after this type DOCKER BUILT -t <nameoftheimage> . to build the docker image in your terminal to build this image from this file



# ---------- WHAT WE LEARNED ------------
# 1 we learned with FROM we SPECIFIED RUNTIME ENVIRONMENT of our application THIS IS THE PARENT IMAGE
# 2 with WORKDIR we specified the root folder of our application
# 3 with COPY we are saying COPY files from THIS PC folder to DOCKER Virtual Machine folder
# 5 with RUN we saying to install all the dependencies our application need
# 6 with EXPOSE we saying expose this PORT 
# 7 with CMD we telling to run this command in TERMINAL it needs to be an array ["node","app,js"] if theres a space add another index for the item
# 8 IMPORTANT make sure to CREATE .dockerignore FILE to ignore certain files and folder to ignore like node_modules
# 9 we BUILD an DOCKER IMAGE with this DOCKERFILE with this COMMAND which is DOCKER BUILD -T <IMAGENAME> . make sure to put that dot

