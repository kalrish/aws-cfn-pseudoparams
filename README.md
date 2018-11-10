AWS CloudFormation pseudo parameters display
===============================================================================

This project provides a CloudFormation template that displays the values of pseudo parameters as stack outputs.


Usage
-------------------------------------------------------------------------------

 1.  Create the CloudFormation macro.
 
     In order to display pseudo parameters, a custom CloudFormation macro is used. To create it, deploy a new CloudFormation stack based on the `cfn/macro.yaml` template:
     
         $  aws cloudformation create-stack --stack-name cfn-pseudoparams --template-body file://cfn/macro.yaml --capabilities CAPABILITY_IAM
         $  aws cloudformation wait stack-create-complete --stack-name cfn-pseudoparams
 
 2.  Display pseudo parameters.
 
     To display pseudo parameters, deploy a CloudFormation stack based on the `cfn/pseudoparams.yaml` template:
     
         $  aws cloudformation deploy --stack-name pseudoparams --template-file cfn/pseudoparams.yaml
     
     By default, almost all pseudo parameters will be displayed. To choose which to display, use the `PseudoParameters` parameter.
