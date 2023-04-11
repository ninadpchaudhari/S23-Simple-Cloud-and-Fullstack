[scale Benefits](https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-benefits.html)
[AWS Docs](https://docs.aws.amazon.com/autoscaling/ec2/userguide/get-started-with-ec2-auto-scaling.html#gs-walkthrough-summary)

# Step 1 : Create a Launch Template

1. Open the `Launch templates` page of the Amazon EC2 console.

2. On the navigation bar at the top of the screen, select an AWS Region. The launch template and Auto Scaling group that you create are tied to the Region that you specify.

3. Choose Create launch template.

4. For Launch template name, enter `my-template-for-auto-scaling`.

5. Under `Auto Scaling guidance`, select the check box.

6. For Application and OS Images (Amazon Machine Image), choose a version of **Amazon Linux 2 (HVM)** from the Quick Start list.

7. For Instance type, choose `t2.micro`


8. For Key pair (login), choose an existing key pair. 

9. For Network settings, Security groups, `Create security group`, then Name your group & add a description.
   - Add a Description
   - Let the default VPC exist. 
   - Click on `Add Security group role` with Port range as `80` and Source type as "Anywhere"
   - Click on `Add Security group role` with Port range as `22` and same source type as earlier
10. Click on `Advanced network configuration`
    - Under `Auto-assign public IP` -> Mark it as enable
11. `Create Launch template` to create the launch template
Choose Create launch template.

On the confirmation page, choose `Create Auto Scaling group`.


# Step 2: To create an Auto Scaling group
1. On the Choose launch template you just created, and for Auto Scaling group name, enter `my-first-asg`.

Choose Next.
**************

Select the Avaliability zones and subnets as your zone ( us-east-1a )

Choose Next.
**************

* Select `Attach to a new load balancer`, with 
  - `Load balancer scheme` as Iinternet facing
  - Availability Zones and subnets -- Tick another avaliability zone in that group.
  - `Default routing (forward to)` as 'Create a target group`

* Under `Health checks`, enable "=`Turn on Elastic Load Balancing health checks`
* Set the `Health check grace period` as `150`
* *** Describe what this setting does? 

Choose Next.
**************
1. Modify `Group size ` with desired capacity
   - Desired : 2
   - Mimimum : 1
   - Maximum : 5
2. Select `Target tracking scaling policy`
   - Any Name!
   - Metric Name : Average CPU utilization
   - Target Value : 30
   - 15 seconds warm up before including in metric
Choose Next, until `Create Autoscaling group`
**************

# Step 3: Verify your Auto Scaling group

1. Open the `Auto Scaling groups page` of the Amazon EC2 console.
2. Select the check box next to the Auto Scaling group that you just created.
3. Choose the second tab, Activity. Under Activity history
