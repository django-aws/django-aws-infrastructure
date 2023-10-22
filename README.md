# django-aws-infrastructure

This is a project to run a django app container on aws with RDS DataBase

## Steps:

1. We'll use ECR to hold our image that we created in the django-aws-backend repo
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/447e4300-6f9d-44b3-9714-88d1e419dfde)
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/4e79a575-e2a4-41e9-ac52-841694f02a80)
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/8a0d5025-4d73-4d0c-8682-e69b7655c897)

2. Then create Network resources( vpc , subnets ,routing tables , Gateway , Nat Gateway "eip") and output Load Palancer domain name :
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/b2e664ec-127b-4f25-b60d-dbb0e9ec7495)
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/1542666d-a035-49ff-97b1-6b8c7f264633)
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/53a3ea36-1071-4d8f-94b9-3e6c752170af)


4. Create Load Palancer for our App:
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/78a4525b-a0ef-43ee-8dc6-6b0494910f52)

5. Create ECS Cluster and service:
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/81d1c9fa-080c-42aa-8992-894b4254c6e7)
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/67aed9cc-d1e4-4794-94b9-f4b63da24ceb)


7. Now our app is published successfully:
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/d28c3414-56e0-4b69-87f5-9867f3d65daa)


8. Create RDS instance and connect it with our App:
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/b4d7dc7c-549b-40f3-bb64-b4abdb042594)

9. You will need to do the django migration command through ssh because if you try to access /admin you will have this Error:
    ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/ba7143f8-69b1-4c1a-b9ed-02ce01a1173e)

    You'll need to install "session-manager-plugin" to access your container via ssh:
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/cbb33989-b66e-4573-b247-f37b9f14b240)

   Now you can access admin succesfully and your RDS instance is now connected successfully:
   ![image](https://github.com/django-aws/django-aws-infrastructure/assets/147988907/9e5898cb-1950-4171-a104-1e0eb7e2edd2)

This Project id based on "https://dev.to/daiquiri_team/deploying-django-application-on-aws-with-terraform-minimal-working-setup-587g"






