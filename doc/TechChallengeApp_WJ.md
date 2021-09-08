**TechChallengeApp - Deployment to Azure**
  As part of the Servian tech challenge, the provided golang application is to be containerized and pushed via an automated build and release process to deploy to a public cloud. 
  
  This has been acheived using a combination of docker containerization technology, azure devops pipelines (build and release). The build pipleines are done using YAML. This builds the Docker image and pushes it to Azure Container registry. The latest image is then pushed using a release pipelines to Azure Container Instance. The latest image is pushed to an azure container using Azure release pipelines that runs Azure CLI tasks.

**Design:**

<img width="602" alt="MicrosoftTeams-image (6)" src="https://user-images.githubusercontent.com/52962568/132550377-1a4dd868-3471-414f-86a3-75e7d88e76ee.png">




**Build:**

 YAML based pipeline on Azure Devops that builds the image based on the Docker file and pushes it to Azure container registry. The latest image pushed to the ACR is tagged as latest, and this tag is used to push the image to the Azure container instance.
 
 
**Release:**

Azure Devops release pipeline tasks have Azure CLI code that creates/updates the Azure Container instance. The piplines have been hosted on the following Azure Devops tenancy / organization:
https://dev.azure.com/waseemjaleel/SvnTest/


**Azure Deployment:**

The following resources are deployed to Azure cloud as part of this release:

- Azure Container Registry (svn-tca-aci-01)
- Azure Container Instance (SVNTCAACR01)

The following image shows a snapshot of the resources in azure:

![image](https://user-images.githubusercontent.com/52962568/132553631-a23f38c0-76a9-4d29-b819-40dd5afafdb8.png)


