-- Deploiement

aws cloudformation package `
  --template-file infrastructure\template.yaml `
  --s3-bucket iabd-sourcecode-management-bucket `
  --output-template-file infrastructure\packaged.yaml

aws cloudformation deploy `
  --template-file infrastructure\packaged.yaml `
  --stack-name fgbossou-lambda-s3-trigger-stack `
  --capabilities CAPABILITY_IAM `
  --no-cli-pager


  -- Supprimer la stack
  aws cloudformation delete-stack --stack-name fgbossou-lambda-s3-trigger-stack
  aws cloudformation wait stack-delete-complete --stack-name fgbossou-lambda-s3-trigger-stack


  learningesgissandbox