# Team1-project
test
1-step.
#Clone a repository
git clone https://github.com/farrukh90/artemis.git

git checkout 2.0.0 (2.0.0 - version...can be any number depending on available and selected version)-to switch to new branch

1.1-scan image
sonarcloud.io
export SONAR_TOKEN="........"

2-step.
#Build docker image
docker build -t artemis:2.0.0  .   (to build regular image)

#authenticate repository
gcloud auth configure-docker \
    us-central1-docker.pkg.dev
    
    
#(adding location of artifacts registry)
docker build -t us-central1-docker.pkg.dev/terraform-project-tamila/artemis/artemis:2.0.0       .  (adding location of artifacts registry)

#SYNTAX OF THE COMMAND 
#us-central1-doecker.pkg.dev = REGISTRY
#terraform-project-tamila = PROJECT_ID
#artemis = NAME_OF_REPOSITORY
#artemis:2.0.0 = NAME_OF_APP:VERSION
#. = Dockerfile location

4-step
#Publish
docker push us-central1-docker.pkg.dev/terraform-project-tamila/artemis/artemis:2.0.0

to scan the image in the Artifact registry we can enable vulnerability scanning.

# TO BUILD A PIPELINE> GH Actions workflow preparation
GITHUB>SETTINGS>SECRETS AND VARIABLES>ACTIONS>
create new secret
PROJECT_ID
your GCP project ID
create new secret
to authenticate Google account to talk to github account SERVICE ACCOUNT must be created 
add key>create new key>use downloaded file in json format
#create new secret
SERVICE_ACCOUNT
insert info from json file


-----------------

To create helm chart
1-mkdir nameoffolder

#command to create helm chart
helm create artemis

 #update values.yaml
 repository:us-central1-docker.pkg.dev/artemis/artemis
 

tag: "latest" 0r 2.0.0
  
  
  port = 5000
  
  #run
  helm install application. ./artemis/
  
  to verify;
  helm list
  
  #update ingress and domain in values.yaml
  enable: true
  className: "nginx"
  enable tls(no brackets)
  host: application.mydomain
  
  helm uninstall
  helm install  application. ./artemis/ #-with installed ingress
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  













