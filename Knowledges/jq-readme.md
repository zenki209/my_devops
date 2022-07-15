#List EC2 Id instances

aws ec2 describe-instances --profile amelia-p --region ap-southeast-1 | jq '.Reservations[].Instances[] | .InstanceId, .State.Name'   

#Get Stop EC2 Instances
aws ec2-describe-instances --filter "instance-state-name=stopped" --profile amelia-p 

#List AMI start with Name
aws ec2 describe-images --owner self --profile amelia-p --region ca-central-1 | jq '.Images[]|select(.Name |contains("iasaws")) | .Name'

## in powershell the " need to be go with \ => so on windows it will be 


aws ec2 describe-images --owner self --profile amelia-p --region ca-central-1 | jq '.Images[]|select(.Name |contains(\"iasaws\")) | .Name'