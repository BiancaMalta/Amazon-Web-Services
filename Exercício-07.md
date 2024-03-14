# Exercício 07
## Crie 2 IAM roles
1. Acesso EC2 com permissão AdministratorAcces
2. Acesso CodeDeploy com permissão CodeDeploy

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/4e4841e4-bc64-4213-a512-609e69a515ab)

## Criar Instancias para rollout do deploy
Crie 2 maquinas com Amazon Linux </br>
Associe a role que voce criou acima  nas 2 ec2 criadas

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/8e3340bf-7626-4f4b-86bc-f16f5b0c1c88)

## Acesse a maquina e execute os seguintes comandos
```
sudo yum update
sudo yum install ruby
sudo yum install wget
cd /home/ec2-user
wget https://aws-codedeploy-eu-central-1.s3.amazonaws.com/latest/install
chmod +x ./install
sudo ./install auto
sudo service codedeploy-agent status
```

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/a640f8c1-61e8-49e8-99d1-4296076e8e00)


## Download the Application Code
1. In a new tab, open the GitHub repository link provided on the lab page and copy the URL.
2. In the AWS Console, click the Cloud Shell icon (>_) in the upper right.
3. Once the session has initialized, enter wget and paste the GitHub URL (do not run the command yet): wget https://github.com/Herikamachado/ExercicioFinal/blob/main/webapp.zip  
4. In the URL, replace blob with raw, then press Enter.
5. Run ls to view the ZIP file.

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/656d9b3b-64f9-42c1-a233-6809c5143e54)

## Create an S3 Bucket
1. In Cloud Shell, create a unique bucket name: aws s3 mb s3://<insert unique name>  
2. Press Enter.
3. Upload the code to the bucket using the bucket name from the previous step: aws s3 cp webapp.zip s3://<insert bucket name>  
4. Type s3 into the search bar at the top of the browser, then click S3 and open in a new tab.
5. Click the bucket listed under Name, then click into webapp.zip.
6. Click Copy S3 URI.
7. s3://herikaada2024/webapp.zip

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/b18bd8a6-32dd-4f71-9b2b-fdaf3d6dc001)

## Deploy the Code Using CodeDeploy
1. In the AWS Console, type ec2 into the search bar at the top of the page. Click EC2.
2. Under Resources, click Instances (running) to view your instances.
3. Note the tag name, demo-server.

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/c601f865-ec69-4016-93d3-e1d210485eef)

4. Type codedeploy in the search bar at the top of the page. Open CodeDeploy in a new tab.
5. From the left-hand menu on the CodeDeploy page, select Getting started.
6. Click Create application.
7. Set the following parameters:
    * Application name: Type mywebapp.
    * Compute platform: Select EC2/On-premises.

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/341043dd-fe4b-4f11-b04f-dbe54a63f61b)

8. Click Create application.
9. On the next page, click Create deployment group.
10. Set the following parameters:
    * Deployment group name: Type mydg.
    * Service role: Select the service role that populates.
    * Deployment type: Select In-place.
    * Environment configuration: Click Amazon EC2 instances.
    * Key: Select Name.
    * Value: Select acg-demo-server.
    * Deployment settings: Select CodeDeployDefault.AllAtOnce.
    * Load balancer: De-select the Enable load balancing box.

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/e38f5d70-3389-465a-ba54-03b5b17f2789)

11. Click Create deployment group.
12. Click Create deployment.
13. For Revision location, copy and paste the bucket from the Cloud Shell, s3://<insert bucket name>/webapp.zip.
14. Scroll to the bottom of the page and click Create deployment (it may take a few minutes to create).
15. Test the deployment by navigating back to the EC2 page and click into one of your instances.
16. Copy the Public IP, then open an incognito browser tab. (Usando porta 80 http)
17. Paste the IP address into the browser tab. You should see a congratulations message appear on the web page.

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/10c8f4d9-956e-4cd9-9b0c-add9fda67845)
