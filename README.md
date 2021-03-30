# AchiStarTechApp
AchiStar Tech Docker Jenkins Pipeline App
simple html file in /public-html to display name of app
Clone the git repo https://github.com/JaneRands/AchiStarTechApp/tree/master and edit index.html.
Once you add, commit, and push your changes to the Git Repository, the Jenkins build will start the Jenkins pipeline defined in the Jenkinsfile. 
The Jenkinsfile clones the AchiStar project from GitHub, builds the Docker image from the Dockerfile, tags it with the build number, then deploys the image to DockerHub as janerands/achistar:build number.
docker pull janerands/achistar:build number then run locally to test your code changes.
