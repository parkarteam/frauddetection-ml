# Building and Installing mymodel
The following instruction are for building and installing the mymodel fraud detection seldon model

## Requirements
Open Data Hub installation with Seldon enabled are described [here](../../../README.md)

## Build mymodel
````
git clone https://gitlab.com/jnakfour/odh-frauddetection.git
cd model/mymodel
vi mymodel.py
Insert all required fields
s2i build . seldonio/seldon-core-s2i-python3:0.4 mymodel
docker tag mymodel:latest <Insert Container Registry Name>/mymodel
docker push <Insert Container Registry Name>/mymodel
````

## Installing mymodel
````
oc login <InsertOpenshift Cluster login>
oc project <Insert Project Name>
vi mymodel.json Insert all required fields
oc create -f mymode.json -n <Insert Project Name>
oc get SeldonDeployments
````
