<h3>AWS Hands-on Tutorials</h3>
<p>October 27 2024<br></p>

![image](https://github.com/user-attachments/assets/731bfaff-0b4f-4866-8f4c-bdce2e76fe57)

<p>Hey there, fellow lifelong learner! I´m <a href="https://www.linkedin.com/in/rosanafssantos/">Rosana</a>, and I’m genuinely excited to join you on this adventure.</p>
<p>It´s key part of my AWS hands-on journey.</p>
<p>Let´s get started!!</p>


<h2>Project Goals</h2>
<p>In this tutorial, we will:
<ul style="list-style-type:square">
    <li>create an on-demand backup job of an Amazon EC2 instance.</li>
    <li>use a backup plan to back up Amazon EC2 resources—using a backup plan within AWS Backup lets you automate your backups on a schedule.</li>
    <li>add resources to an existing backup plan using tags</li>
</ul></p>

<h2>Prerequisites</h2>
<p>We will need the following resources or permissions to proceed:
<ul style="list-style-type:square">
    <li>an AWS account.</li>
    <li>one or more Amazon EC2 instaces.</li>
    <li>IAM roles used by AWS Backup to create a backup of the Amazon EC2 instance.</li>
</ul></p>

<h2>Create one <code><em>Amazon EC2</em></code> instance</code></h2>

![image](https://github.com/user-attachments/assets/117acb6a-dde8-4d39-9074-abf341e9829b)

<br>

![image](https://github.com/user-attachments/assets/106cecc0-fbd8-493f-b6cd-654b8a25c78a)

<br>

![image](https://github.com/user-attachments/assets/0ffc405b-f9de-404d-a714-df144ffc1b17)

<br>

![image](https://github.com/user-attachments/assets/500feddd-6787-481c-adaf-b9cbfa1a466d)

<br>

![image](https://github.com/user-attachments/assets/eb4d42cd-3e39-47b3-b509-7d9530854973)

<br>

![image](https://github.com/user-attachments/assets/28293916-fb38-4258-aab6-726b7e9c57cd)

<br>

![image](https://github.com/user-attachments/assets/6ffcf605-4410-479f-a2ba-ed14b97c114c)

<div align="center">

<center><h2><strong><code><em>Amazon EC2</em></code> instance created</strong>!!!</h2><br><br></center>

</div>
<br>
<br>

<h2>Access <code>AWS Management console</code> and <code>AWS Backup console</code></h2>
<p>Log in to the <a href="https://console.aws.amazon.com/">Amazon Management console</a>, and open the <a href="https://console.aws.amazon.com/backup">Amazon Backup console</a> </p>

![image](https://github.com/user-attachments/assets/0f041f0a-23e6-4a84-adf9-06e58d1e4b3b)

<br>

![image](https://github.com/user-attachments/assets/1e8ed02d-1a92-454c-8cbb-552edc93c7e8)

<br>

<h2>Configure an on-demand <code><em>AWS Backup</em></code> Job for one <code><em>Amazon EC2</em></code> instance</h2>
<h3<code>Configure the services used with AWS Backup</h3</code></h3>

<p>In the navigation pane on the left side of the <code><em>AWS Backup</em></code> console, under <code>My account</code>, choose <code>Settings</code>.</p>

<p>On the <code>Service opt-in</code> page, choose <code>Configure resources</code>.</p>

<p>On the <code>Configure resources</code> page, use the toggle switches to enable or disable the services used with <code><em>AWS Backup</em></code>. In this case, select <code>EC2</code>. Choose <code>Confirm</code> when your services are configured.<br>
AWS resources that you're backing up should be in the same Region of this activity, and resources must all be in the same AWS Region.</p>

![image](https://github.com/user-attachments/assets/fa77eb6d-1c96-4803-b353-4d23183c4997)

<h3><code>Create an on-demand backup Job of and Amazon EC2 instance</code></h3>

<p>Back in the <code><em>AWS Backup</em></code> console, under <code>My account</code> in the left navigation pane, select <code>Protected resources</code>.</p>

![image](https://github.com/user-attachments/assets/373e47ea-7f98-403f-b920-4c09678d066a)

<p>From the dashboard, choose the <code>Configure on-demand backup</code> button.</p>

![image](https://github.com/user-attachments/assets/aa679843-5bc4-4965-96f8-560e0d6039b9)

<p>on the <code>Configure on-demand backup</code> page, choose the following options:</p>
<ul style="list-style-type:square">
    <li>Select the resource type that you want to back up; for example, choose EC2 for <code><em>Amazon EC2</em></code>.</li>
    <li>Choose the <code>Instance ID</code>code> of the EC2 resource that you want to protect.</li>
    <li>Ensure that <code>Create backup now</code> is selected. This initiates your backup job immediately and enables you to see your saved resource sooner on the <code>Protected resources</code> page.</li>
    <li>Select the desired <code>retention period</code>. <code><em>AWS Backup</em></code> automatically deletes your backups at the end of this period to save storage costs for you.</li>
    <li>Choose an existing backup vault. Choosing <code>Create new Backup vault</code> opens a new page to create a vault and then returns you to the Create on-demand backup page when you are finished.</li>
    <li>Under <code>IAM role</code>, choose <code>Default</code> role. Note: If the AWS Backup Default role is not present in your account, then an <code><em>AWS Backup</em></code> Default role is created with the correct permissions.</li>
    <li>Choose the <code>Create on-demand backup</code> button. This takes you to the Jobs page, where you will see a list of jobs..</li>
</ul></p>

<p>On the <code>Service opt-in</code>code> page, choose <code>Configure resources</code>.</p>

![image](https://github.com/user-attachments/assets/02186e51-3b92-4638-a049-66353203e81e)

<br>

![image](https://github.com/user-attachments/assets/26764a11-110b-4054-9dcc-8620824f2adc)

<br>

![image](https://github.com/user-attachments/assets/56322393-9499-40f0-a103-93524ae2184f)


<p>Choose the <code>Backup Job ID</code> for the resource that you chose to back up to see the details of that job.</p>

![image](https://github.com/user-attachments/assets/d37244bd-6c0c-408b-ac7a-d1f3dae680e3)

<br>

![image](https://github.com/user-attachments/assets/c2076aa6-f6c9-490a-bb26-f428c2530843)

<br>

![image](https://github.com/user-attachments/assets/7d0d85e4-aa33-4f14-8c64-2cc4a0ce9233)

<br>

![image](https://github.com/user-attachments/assets/3a4c6646-d103-4003-83ff-0aa7a09e2691)

<div align="center">

<h2><strong><code><em>AWS Backup</em></code> Job is configured for an <code><em>Amazon EC2</em></code> instance!!!</strong></h2><br><br>

</div>
<br>
<br>

<h2>Configure an <code>automatic</code> <code><em>AWS Backup</em></code> Job for one <code><em>Amazon EC2</em></code> instance</h2>
<h3>Configure the services used with <code><em>AWS Backup</em></code> and configure a backup plan for one <code><em>Amazon EC2</em></code> instance</h3>

![image](https://github.com/user-attachments/assets/c008829c-99d5-4079-897a-e2219218a73f)

<br>

![image](https://github.com/user-attachments/assets/431e8ead-8fe2-4ffa-95bf-d2d233da990b)

<br>

![image](https://github.com/user-attachments/assets/d94d0ea6-1ee4-4b1d-99f0-c23cbd5b7b9f)

<br>

![image](https://github.com/user-attachments/assets/221c9c6b-56ce-4080-ab49-455a2e0001ba)

<br>

![image](https://github.com/user-attachments/assets/ff15f725-06be-4873-ae85-0109bdf20626)

<br>

![image](https://github.com/user-attachments/assets/684b049d-e7ab-491c-9af2-d243f90bb4d5)

<br>

![image](https://github.com/user-attachments/assets/c1e49e88-fdcb-491e-861d-4d4abb3fd23e)

<br>

![image](https://github.com/user-attachments/assets/cfc19cd6-621b-4982-9745-d9c7cede89a4)

<br>

![image](https://github.com/user-attachments/assets/3265a6c5-bceb-4a7d-a475-a4f45a16fe23)

<div align="center">

<h2>Configured an <code>automatic</code> <code><em>AWS Backup</em></code> Job for one <code><em>Amazon EC2</em></code> instance !!!</h2><br><br>

</div>
<br>
<br>

<h3>Assign resources to the Backup Plan</h3>

![image](https://github.com/user-attachments/assets/5584e946-bd76-4b12-92ef-d6c9540f36c4)

<br>

![image](https://github.com/user-attachments/assets/b7f6a789-aab7-4388-8c21-609f9c2c291b)

<br>

![image](https://github.com/user-attachments/assets/db8a59aa-39c9-46fd-9287-75d71141f33d)

<br>

![image](https://github.com/user-attachments/assets/f151ec2e-7a4a-4ce7-afff-22fa3ab3753a)

<div align="center">

<h2><strong>Resource assigned to the <code>Backup Plan</code>!!!</strong></h2><br><br>

</div>
<br>
<br>

<p>Check Backup Plan = OK</p>
    
![image](https://github.com/user-attachments/assets/fca7b26b-f419-4672-b95f-f211c97d8c03)

<p>Checked Protected Resource = OK</p>

![image](https://github.com/user-attachments/assets/d186931b-82c7-4362-9e65-1c4ad25cc12b)

<p>Check Job = OK</p>

![image](https://github.com/user-attachments/assets/860c9acd-5164-4213-9b93-c9c0293c0163)


<h2>Restore an <code><em>Amazon EC2</em></code> using <code><em>AWS Backup</em></code></h2>
<h3><code>Navigate to the backup vault that was selected in the backup plan and select the latest completed backup.</code></h3>
<h3><code>To restore the EC2 instance, select the recovery point ARN and choose Restore.</code></h3>
<h3><code>The restore of the ARN will bring you to a Restore backup screen that will have the configurations for the EC2 instance using the backed-up AMI and all the attached EBS volumes.</code></h3>
<ul style="list-style-type:square">
    <li>In the Network settings pane, accept the defaults or specify the options for the Instance type, Virtual Private Cloud (VPC), Subnet, Security groups, and Instance IAM role settings.</li>
    <li>This example proceeds with no IAM role. The IAM role can be applied to the EC2 instance after the restore process is completed.</li>
</ul></p>


<h3>In the Restore role pane, accept the Default role or Choose an IAM role to specify the IAM role that AWS Backup will assume for this restore.</h3>
<h3>In the Advanced settings pane, accept the defaults or specify the options for Shutdown behavior, Stop - Hibernate behavior, Placement group, T2/T3 Unlimited, Tenancy, and User data settings. This section is used to customize shutdown and hibernation behavior, termination protection, placement groups, tenancy, and other advanced settings.</h3>
<h3>AWS Backup will use the SSH key pair used at the time of backup to automatically perform your restore.</h3>
<h3>After specifying all of your settings, choose Restore backup. The Restore jobs pane will appear, and a message at the top of the page will provide information about the restore job.</h3>
<h3>Check for your restored backup job under Restore jobs in the the AWS Backup console.</h3>
<h3> Once the job status appears as completed, navigate to the Amazon EC2 console and select Instances in the left navigation pane to see the restored EC2 instance. The EC2 instance is restored using the backup of the AMI and the attached EBS volume.</h3>


![image](https://github.com/user-attachments/assets/cc407772-084c-4a8e-b49e-0b03fd44578b)


<br>

![image](https://github.com/user-attachments/assets/1ecbaaea-5b40-4420-9d41-5c3ff5cc373e)



<div align="center">

<h2><strong>Congratulations!!!<br>
We created a backup of one <code><em>Amazon EC2</em></code> instance and performed a restore using <code><em>AWS Backup</em></code> </strong></h2><br><br>

</div>
<br>
<br>

<h2>Enabled <code><em>Amazon EC2</em></code> monitoring through <code><em>AWS CloudWatch</em></code></h2>

![image](https://github.com/user-attachments/assets/b7d3551e-c68d-4d19-a82e-07ff28c9a0c8)

![image](https://github.com/user-attachments/assets/e81da8bd-1b25-45af-ad2d-ae04600dd518)

![image](https://github.com/user-attachments/assets/ff2c6d1e-6179-448a-98af-54673855d036)


![image](https://github.com/user-attachments/assets/b65ba03f-b401-402b-aa53-6d1e0302e3d3)

![image](https://github.com/user-attachments/assets/9be30bdd-bfb8-4098-9c25-8dede7404a13)



Reference: https://aws.amazon.com/getting-started/hands-on/amazon-ec2-backup-and-restore-using-aws-backup/?ref=gsrchandson&id=itprohandson

