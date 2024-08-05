# IAMOPS TAG

Steps to deploy this stack
1. Run the below command in the ec2 instance

curl -LO https://raw.githubusercontent.com/biradarganesh5/iamopstag/main/deploy_autotag.sh


2. Make a cloudtrail and a bucket in us-east-1

3. Upload the 0.5.7.zip in this repo to the bucket you made in the following directory 
    s3://$YOUR_BUCKET_NAME/releases/autotag-0.5.7.zip

4. Now run the following command in your ec2 instance

    ./deploy_autotag.sh --region us-east-1 --s3-bucket $YOUR_BUCKET_NAME --release-version 0.5.7 create

5. After successfull deployment of the above command, Run the below command

    ./deploy_autotag.sh -r us-east-1 -s3bu $YOUR_BUCKET_NAME update-master

6. To give custom tags 

    ./deploy_autotag.sh -r us-east-1 -s3bu $YOUR_BUCKET_NAME update-master --custom-tags '{"AutoTag_ManagedBy": "Site Reliability Engineering"}'

7. Enjoy HF!
