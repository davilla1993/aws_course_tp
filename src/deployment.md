aws cloudformation package `
  --template-file infrastructure\template.yaml `
  --s3-bucket iabd-sourcecode-management-bucket `
  --output-template-file infrastructure\packaged.yaml


  aws cloudformation deploy `
  --template-file infrastructure\packaged.yaml `
  --stack-name fgbossou-lambda-s3-trigger-stack `
  --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM