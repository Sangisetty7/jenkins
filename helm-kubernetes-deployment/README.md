## Helm Deployment using Jenkins Pipeline to Kubernetes

You can find the Jenkinsfile above, but you need to do some configurations for the Jenkins to make the pipeline work successfully.

### Prerequisites

**Step 1:**
      When you run pipeline the namespaces won't get created because of not having rbac permission, so add clusterrolebinding for the namespace where jenkins is deployed. 
 
 ``` kubectl create clusterrolebinding jenkins-admin-binding --clusterrole=cluster-admin --serviceaccount=<jenkins_deployed_namespace>:default ```

**Step 2:**  When you check the pipeline you need to pass four varaibles, you can pass then as env, which you can configure in Jenkins UI -> **Manage Jenkins** -> **Configure System** -> **Global Parameters** you can find environment varaibles.

**Step 3:**  You have to pass these four env varaibles 
* **namespace** -> Namespace name where you want to deploy helm.
* **release** -> Name for your helm release.
* **HELM_REPO** -> Helm Repository link.
* **chart_name** ->  Helm chart name, you can find this with the help of command "helm search repo <repo_name>".
