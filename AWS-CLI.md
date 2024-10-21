<h3>PROZ AWS Arquitet@s Program</h3>
<h1> Using the <code>AWS CLI</code> installed on Windows, I created a <strong><em>VPC</em></strong> that includes both a <strong><em>public and private subnet</em></strong> within the same Availability Zone, attached an <strong><em>Internet Gateway</em></strong>, and configured the <strong><em>Route Table</em></strong>.</h1>
<p>October 21, 2024<br></p>

<p>This highlighted in green is the architecture created.</p>

![image](https://github.com/user-attachments/assets/5b0d78f3-a328-4811-a825-90341effb2ad)

<p></p>
<p>I started creating a VPC.</p>


![image](https://github.com/user-attachments/assets/af18e270-8288-4dc4-a407-0b189b5d1de8)

![image](https://github.com/user-attachments/assets/e0f49ac5-de4b-4de3-847c-39a4c1ed2fba)

<p>After running
<pre><code>
aws ec2 create-vpc --cidr-block 172.20.0.0/16
</code></pre>
I got the following output.</p>

<pre><code>
{
    "Vpc": {
        "CidrBlock": "172.20.0.0/16",
        "DhcpOptionsId": "dopt-00b416862a2f77fb1",
        "State": "pending",
        "VpcId": "vpc-00590e188b434d1fb",
        "OwnerId": "712107929769",
        "InstanceTenancy": "default",
        "Ipv6CidrBlockAssociationSet": [],
        "CidrBlockAssociationSet": [
            {
                "AssociationId": "vpc-cidr-assoc-0ec9980bc043c81b5",
                "CidrBlock": "172.20.0.0/16",
                "CidrBlockState": {
                    "State": "associated"
                }
            }
        ],
        "IsDefault": false
    }
}
</code></pre>

<p>Here is the breakdown of each part of my output.</p>
<ul>
    <li>CidrBlock: "172.20.0.0/16" shows that the VPC was created with the correct CIDR block you specified.</li>
    <li>DhcpOptionsId: This is the ID of the DHCP options set associated with the VPC.</li>
    <li>State: "pending" means the VPC creation is in progress. It generally transitions to "available" shortly after creation.</li>
    <li>VpcId: "vpc-00590e188b434d1fb" is the unique identifier for your new VPC. You'll use this ID for further configurations and operations.</li>
    <li>OwnerId: This indicates the AWS account owner of the VPC.</li>
    <li>InstanceTenancy: "default" means instances launched in the VPC will have the default tenancy.</li>
    <li>CidrBlockAssociationSet: Shows the CIDR block association details, confirming that the CIDR block is successfully associated with your VPC.</li>
</ul>