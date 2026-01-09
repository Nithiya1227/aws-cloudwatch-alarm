# AWS CloudWatch CPU Utilization Alarm with SNS Email Notification

## 📌 Project Overview
This project demonstrates how to monitor EC2 CPU utilization using **Amazon CloudWatch** and receive **email notifications via Amazon SNS** when CPU usage crosses a defined threshold.  
The project follows **AWS Free Tier–safe practices** and includes hands-on testing using Linux CPU stress.

---

## 🏗️ Architecture Overview
The solution consists of:
- An Amazon EC2 instance (Amazon Linux 2023)
- Amazon CloudWatch for metrics and alarms
- Amazon SNS for email notifications
- CPU stress testing using Linux `stress` utility

## 📷 Architecture diagram is included in this repository.
 [Architecture overview](architecture-cloudwatch.png)

---

## 🔧 Services Used
- **Amazon EC2**
- **Amazon CloudWatch**
- **Amazon SNS**
- **Amazon Linux 2023**
- **Stress (Linux utility)**

---

## ⚙️ Project Workflow
1. Launch an EC2 instance (Free Tier eligible)
2. Monitor CPU utilization using CloudWatch metrics
3. Create a CloudWatch alarm based on CPU threshold
4. Configure SNS topic with email subscription
5. Attach SNS topic to the CloudWatch alarm
6. Generate CPU load using `stress` to test monitoring
7. Receive SNS email notification (tested successfully)

---

## Alarm Configuration
Metric Name: CPUUtilization
Namespace: AWS/EC2
Threshold: CPU Utilization > 50%
Evaluation Period: 1 datapoint within 1 minute
Alarm Actions: Send notification via SNS email



## 🧪 Testing & Validation
To validate the alarm behavior:
CPU load was generated on the EC2 instance using a stress testing utility
CloudWatch CPU metrics were monitored in real time
SNS email notification functionality was tested using the SNS Test Message feature



## Note:
SNS email delivery was validated using an SNS Test Message.
CloudWatch alarm state may vary depending on EC2 instance size and workload behavior in the AWS Free Tier.



## 📸 Screenshots (Proof of Work)
[CloudWatch Alarm](screenshots/cloudwatch.png)
[terminal sns](screenshots/terminal-sns.png)
[SNS Email Notification](screenshots/sns-mail-msg.png)



## 💰 Cost & Free Tier Safety
All resources were created and tested within AWS Free Tier limits
EC2 instance, CloudWatch alarms, and SNS were used minimally
All resources were stopped or deleted after testing to avoid unnecessary charges



## 🎯 Key Learnings
Hands-on experience with AWS monitoring and alerting
Understanding CloudWatch metrics and alarm states
Practical use of SNS for operational notifications
Real-world alerting setup used in production systems



## ✅ Project Status
✔ Successfully completed and validated



## 🔔 Alert Validation Note
Due to AWS Free Tier constraints and low CPU burst behavior, the CloudWatch alarm threshold was not force-triggered during testing.
However, the end-to-end alerting pipeline was successfully validated by:
Confirmed CloudWatch alarm configuration
Verified SNS topic subscription
Successfully receiving SNS test email notifications
This confirms that the monitoring and notification setup is functioning as expected in a real-world environment.



## 📌 This project demonstrates real-world AWS monitoring skills suitable for junior cloud engineer and fresher roles.
