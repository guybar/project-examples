# HashiCorp Vault example
This is an example of a GitLab pipeline which uses HashiCorp Vault to issue an artifactory short lived token 
based on GitLab JWT.

## Preparations
In order to be able to run this example, aa hashicorp vault instance should be used and configured 
based on the following documentation:
https://docs.google.com/document/d/1k1C4xDWXLzgIY6FzCisEYGb-2c8Xv8ts3XxgrJGl8nk/edit#

## Configuring the GitLab project
1. Create a GitLab project
2. Import a Gradle repository into the project (I used https://github.com/spring-projects/spring-petclinic)
3. Configure the following variables in GitLab (Settings->CI/CD->Variables):
   1. VAULT_URL - the HashiCorp Vault URL
   2. JFROG_PLATFORM_URL - the JFrog platform server URL
 
4. Create a new pipeline in GitLab and copy the content of gitlab-ci.yml file to it

## Running the pipeline
By default GitLab pipelines are triggered whenever a change is commited to the project repo.
However, you can manually trigger the pipeline by going to: CI/CD->Pipelines and press the "Run pipeline" button.
To view the pipeline execution logs navigate to: CI/CD->Jobs, and click the required job execution line.

