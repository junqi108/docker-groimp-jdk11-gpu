# groimp-docker

## This is a general Docker container to run GroIMP 1.6 with java 11. It can be map to the folder structure of the model with docker-compose file 
## A docker file is a isolated environment for running specific applications. It can run independently from the local environment. 
## a general workflow for using this docker file is use it as the groimp application, write docker-compose script to map the model, and run the model from a docker compose file

## need to add ext folder for jocl.jar, jogl.jar, gluegen-rt.jar
## lauch groimp
java "-Xmx${JAVA_XMX}M" -Xverify:none -cp "${GROIMP_DIR}/jocl.jar:${GROIMP_DIR}/jogl.jar:${GROIMP_DIR}/gluegen-rt.jar" --module-path "${GROIMP_DIR}/Platform-Core/:${GROIMP_DIR}/Graph/:${GROIMP_DIR}/Utilities/:${GROIMP_DIR}/XL-Core/" --module platform.core/de.grogra.pf.boot.Main --project-tree

#### Due to Oracle's authentication requirement, users need to download the java version by themselves and put into the java folder before running the docker build



