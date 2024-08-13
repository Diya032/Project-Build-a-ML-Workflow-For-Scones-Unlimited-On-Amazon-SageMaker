# Project-Build-a-ML-Workflow-For-Scones-Unlimited-On-Amazon-SageMaker

* lambda.ipynb : Submittion of consolidated code for 3 Lambda Functions
* starter.py: Main code
* step_function images: success in workflow
* step function definition in JSON and yaml format

  ## Steps to keep in mind
  ### Second Lambda function :
    * Add packaged dependency (sagemaker) as a layer while creating lambda function
    * In sagemaker studio main directory: (TERMINAL)
        * mkdir python
        * pip install --target ./python sagemaker
        * sudo apt install zip (downloading zip)
        * zip -r sagemaker.zip ./python/
        * aws s3 cp ./sagemaker.zip s3://<bucket_name>/
    * Set Lambda 2 function in 3.10 runtime environment (version compatability with sagemaker)
    * Set Layer runtime environment as 3.10 as well (version compatability with sagemaker)
    * Go to Second Lambda function IAM role , create inline policy , Add code to allow access invokation of sagemaker endpoint, save 
    * Don't forget to attach sagemaker execution policy to this role (second lambda function) as well
    * Get Endpoint from sagemaker studio > (left-hand-menu) Deployment > Endpoints
    
