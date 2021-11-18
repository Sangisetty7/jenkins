Jenkins Pipeline is a powerful tool when you are using Jenkins to automate your deployments. Flexible and customized actions split between stages are a good reason to try this feature.

Building your own Docker Image and uploading it to Docker Hub to keep your repository updated is a good example to understand how Jenkins Pipelines can improve your way of work.

Prerequisites

    A server with Jenkins and Docker running on it (Jenkins user should be allowed to run Docker).
    Github account.
    Docker Hub account.

Setting Up Your Environment

Install the Docker Pipelines plugin on Jenkins:

Manage Jenkins → Manage Plugins.

Search Docker Pipelines, click on Install without restart and wait until is done.
Upload your Dockerfile definition to your Github repository. Click on the green button Clone or Download and copy the URL as you will need it later.

On Jenkins, you need to create a new credential with your Docker Hub account details. Go to Credentials → Global → Add credentials, and fill out the form with your username and password. Fill in ID and Descriptions. Note that if you set the ID, you will need this specific ID to refer this credential from your scripts. Here we are just using dockerhub_id.


Creating Your First Jenkins Pipeline

Now, we are ready to create our first Pipeline. On Jenkins go to  New Item → Pipeline, type the name you want for this Pipeline project and then click OK.

Following that, you can skip all General and Build Trigger options and go straight to the Pipeline section. Here, you can include a Pipeline definition (usually named Jenkinsfile), or you can refer to an external location like Git or Subversion.

The Pipeline we are defining have four stages:

    The first one is to get the Dockerfile from our Github repository.

    The second one will build the image using $BUILD_NUMBER to tag the version.
    The third one is pushing the built image to your Docker Hub registry.
    Finally, we will cleanup the previously built image on the local server.

Please note that you need to modify the code with your specific Docker Hub and Github details:

Some ideas to go further with Jenkins:

    Define a webhook to run Pipeline when a commit is submitted to your Github repository.
    Include several containers in the same pipeline to keep different stages (like backend and frontend) or different environments (dev/prod)
    Set a notification by Email/Telegram/Slack with the status and/or output of your Pipeline.
