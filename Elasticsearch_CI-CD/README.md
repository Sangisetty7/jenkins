## Elasticsearch deployment using Jenkins
### Prerequisites
* Package the elasticsearch helm chart into .tar -> Using "helm package" command
* Add it to master branch -> create an index for that package "helm repo index . " -> Push it to master branch "git push origin master"
* Finally update the settings in Github pages.
* Now you can add the repo 
