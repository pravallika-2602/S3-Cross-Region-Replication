# S3-Cross-Region-Replication


## Cross Region Replication  
In this document we will learn how to replicate objects from one region to another region 
## Part 1: Create source bucket  
1. Login to aws console. 
2. Click on s3 service. 
3. Click on create bucket

<img width="448" alt="image" src="https://github.com/user-attachments/assets/216fb7e7-68be-4b18-9bd8-b9d0de7dec0a" />

4.Click on general purpose and name it.

<img width="468" alt="image" src="https://github.com/user-attachments/assets/afa89a39-fdac-499a-b6c2-508f646362c7" />

5.Uncheck block all public access

<img width="468" alt="image" src="https://github.com/user-attachments/assets/c42017e3-cb2b-473f-8f2f-886432f3050e" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/33888437-29b7-4ff6-b52b-0803a2cafb15" />
6.Enable bucket versioning  and tags empty
<img width="468" alt="image" src="https://github.com/user-attachments/assets/50f02785-bce7-4e07-a5c3-99e8a8e174df" />
7.Select default encryption as server side encryption amazon s3 managed keys.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/11ddeae3-1f79-4938-9e10-00084e55a006" />
8.Goto advanced settings disable object lock and then click on create bucket.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/faa8e18a-a6eb-4ad0-81bc-3b52953a66eb" />
9.Bucket created successfully.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/0b483896-3ffb-48c1-9b8f-ff1fad0eb614" />
10.Click on created bucket and upload files.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/456f1069-f8f0-4a77-9da1-624efed28310" />
11.Files uploaded successfully.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/35bb0043-8901-4328-9450-808b70a52de2" />
12.Goto source replica bucket and Click on ‘Static Website Hosting’ and put checkmark to ‘Use this bucket to host a website’ and enter ‘index.html’ as default file.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/efa74424-a5b8-4839-bbab-e08ac056e7ac" />
<img width="468" alt="image" src="https://github.com/user-attachments/assets/5effec78-d17d-41d9-abd2-34fd785b6f45" />
13.Scroll down and click on bucket policy and entered as shown below and click on save.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/d874347e-e9a4-426f-a5c9-785b467f3452" />
<img width="468" alt="image" src="https://github.com/user-attachments/assets/444abd60-6aa0-49cb-be10-ed21bd5471d1" />

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::source.replica.durga/*"
        }
    ]
}


<img width="468" alt="image" src="https://github.com/user-attachments/assets/81cfaa61-d29b-4230-85bb-88256c0472d1" />
14.Open end point in browser now you will see the data.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/1899ff0a-f9d6-460b-b19f-916bce1b0ac7" />

Output:
<img width="468" alt="image" src="https://github.com/user-attachments/assets/503e7359-dc48-494e-9b7e-6c71991096a6" />

Part 2: create destination bucket as same as source bucket.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/167b519d-720e-417e-a002-c62997bbc4c0" />
<img width="468" alt="image" src="https://github.com/user-attachments/assets/7768d82e-66aa-4dea-91ed-3f9c90782e9b" />
<img width="468" alt="image" src="https://github.com/user-attachments/assets/5995f0fe-88d4-4ead-8d89-12abfea05b2e" />
<img width="468" alt="image" src="https://github.com/user-attachments/assets/d3f7aba0-dbbb-4a7c-91bd-e6bdb683caa8" />

Part 3: login in to IAM service and create IAM policies.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/6a7730ab-950f-4d4c-a184-1526b6944da6" />
15.Click on create policy. A create policy window opened.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/c7a6c2fc-909f-4d6d-b3d7-02cd97fba386" />
16.Now click on JSON and then enter policy
<img width="468" alt="image" src="https://github.com/user-attachments/assets/e95de491-d3bb-469c-8a89-f5f8f4db217f" />
After entering policy details enter name and description of the policy.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/fbb347c9-9a28-4620-aa68-d3b263619460" />
Click on create policy.
<img width="468" alt="image" src="https://github.com/user-attachments/assets/db78d8b8-f53f-4301-9710-be007c78d665" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/b5a2f8e2-f542-4a7b-a1e4-29b303e20051" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/8a6871f7-80fa-4c70-bc4c-08e8668d8be1" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/a7bd8dc5-7e60-4c05-be85-535cb66672a5" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/be754fe2-4ae9-4173-85c7-5ffbfba0ec67" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/1dc50e55-86ca-4bae-906d-08a4bb3ad71f" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/1a96028d-0bb9-4619-8f43-f7c396a9dde9" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/eef03212-2344-4d36-921b-71b1cadad7ba" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/800406c7-f89f-49fe-8d5f-023cea8c59c0" />

Part:4 Configuring Bucket relica
<img width="468" alt="image" src="https://github.com/user-attachments/assets/d62b085f-b0f8-495f-b7a7-99a1af1e40ab" />
<img width="468" alt="image" src="https://github.com/user-attachments/assets/a13dc793-767a-461e-bc8d-a9dfa620261a" />
Create replication rules:
<img width="468" alt="image" src="https://github.com/user-attachments/assets/35dc092a-6fe9-486e-a13f-07bdfd2bfdac" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/5e6334d0-d32b-47ec-8f21-a3af50ff6afd" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/cc1122fe-e402-4d75-9a69-5019d89d0c18" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/ec3be7be-0859-404e-a11b-c6255e847636" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/c0117923-750f-4b59-8412-892d91c5e683" />

<img width="455" alt="image" src="https://github.com/user-attachments/assets/c407bebe-34f6-4c50-aa0f-535cd09cdc6b" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/2c76cb59-14f5-4513-9080-f931f039466e" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/978f64b7-a256-4920-bf81-353296f4448e" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/70a4e1ce-4307-4498-b2bb-aa51cd7e24ae" />


Update html file as 
<html>
    <head>
        <title> Cutest Cat </title>
    </head>
    <body>
        <center><h1> My Cutest Cat Version 2 </h1><center>
        <center><img src="cat.jpg" alt="Cutest Cat"</center>
    </body>
</html>


<img width="468" alt="image" src="https://github.com/user-attachments/assets/246dcf29-f07f-442c-88f8-35965dff19c1" />

Go to destination replica Now you can see the files automatically copied from one region to another region.

<img width="468" alt="image" src="https://github.com/user-attachments/assets/f4336bc7-b1de-4725-a723-ba01c3a1b91a" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/e557993c-34a5-482f-9f82-4bd0c31ae8c3" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/04d57561-5afc-4453-b378-dd11b233e7d1" />












