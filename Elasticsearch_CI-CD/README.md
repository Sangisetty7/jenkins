## Elasticsearch deployment using Jenkins
### Prerequisites
* Package the elasticsearch helm chart into .tar -> Using "helm package" command   - In Terminal Using Git
* Add it to master branch -> create an index for that package "helm repo index . " -> Push it to master branch "git push origin master"
* Finally update the settings in Github pages.  - In GitHub
* Now you can add the repo using the link available in gh-pages. 

### Procedure
* Just add environment varaibles and you can run the pipeline using the above Jenkinsfile.
* It is CI/CD so whatever you update here will get reflected and pipeline will run.
