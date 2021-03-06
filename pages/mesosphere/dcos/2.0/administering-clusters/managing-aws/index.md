---
layout: layout.pug
navigationTitle:  Managing AWS
title: Managing AWS
menuWeight: 9
excerpt: Scaling your AWS cluster
enterprise: false
render: mustache
model: /mesosphere/dcos/2.0/data.yml
---

You can scale your AWS&reg; cluster or change the number of agent nodes.

## Scaling an AWS cluster

The DC/OS&trade; AWS&reg; CloudFormation template is optimized to run DC/OS, but you might want to change the number of agent nodes based on your needs.

<p class="message--warning"><strong>WARNING: </strong>Scaling down your AWS cluster could result in data loss. We recommend that you scale down one node at a time, letting the DC/OS service recover. For example, if you are running a DC/OS service and you scale down from 10 to 5 nodes, this could result in losing all the instances of your service.</p>


To change the number of agent nodes with AWS:

1.  From [AWS CloudFormation Management][3] page, select your DC/OS cluster and click **Update Stack**.
2.  Click through to the **Specify Parameters** page, and specify new values for the **PublicSlaveInstanceCount** and **SlaveInstanceCount**.
3.  On the **Options** page, accept the defaults and click **Next**. **Tip:** You can choose whether to rollback on failure. By default this option is set to **Yes**.
4.  On the **Review** page, check the acknowledgement box and then click **Create**.

Your new machines will take a few minutes to initialize. You can watch them in the EC2&reg; console. The DC/OS web interface updates as soon as the new nodes register.

 [2]: /mesosphere/dcos/2.0/installing/evaluation/community-supported-methods/aws/
 [3]: https://console.aws.amazon.com/cloudformation/home
